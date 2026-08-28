# React & TypeScript Best Practices Guide

Tài liệu này tổng hợp các nguồn định nghĩa, nguyên tắc kiến trúc và thực hành tốt nhất (Best Practices) khi phát triển ứng dụng với **React** và **TypeScript**.

---

## 1. Nguồn định nghĩa chính thức (Official Documentation)

Đây là nguồn cốt lõi xác định cách code chuẩn theo tư duy của đội ngũ phát triển:

- **[React Official Docs (react.dev)](https://react.dev)**:
  - **Thinking in React**: Cách bóc tách component và tổ chức luồng dữ liệu một chiều (one-way data flow).
  - **Managing State & Escape Hatches**: Quy tắc sử dụng Hooks đúng cách, tránh lạm dụng `useEffect`, nguyên tắc _Single Source of Truth_ và _Derived State_.
- **[TypeScript Handbook (typescriptlang.org)](https://www.typescriptlang.org/docs/)**:
  - Định nghĩa hệ thống kiểu dữ liệu (Type System), phân biệt `type` vs `interface`, Generics, Type Narrowing, Discriminated Unions và Utility Types.
- **[Next.js Docs (nextjs.org/docs)](https://nextjs.org/docs)**:
  - Kiến trúc React Server Components (RSC) vs Client Components (`"use client"`).
  - Tổ chức thư mục dự án và Routing Conventions trong App Router (`src/app`, `src/components`, `src/lib`, v.v.).

---

## 2. Tiêu chuẩn cộng đồng & Cheatsheet thực chiến

- **[React TypeScript Cheatsheet](https://react-typescript-cheatsheet.netlify.app/)**:
  - Cẩm nang chuẩn mực nhất cho việc kết hợp React + TypeScript.
  - Hướng dẫn typing chính xác cho Props, Hooks (`useState`, `useReducer`, `useRef`), Event Handlers (`onClick`, `onChange`), `React.ReactNode` vs `React.JSX.Element`, Generic Components.
- **[Bulletproof React](https://github.com/alan2207/bulletproof-react)**:
  - Kiến trúc thư mục chuẩn cho dự án quy mô vừa và lớn (Feature-based structure, Domain-driven components, Co-location).
- **[Airbnb React/JSX Style Guide](https://github.com/airbnb/javascript/react)**:
  - Quy chuẩn đặt tên: `PascalCase` cho Component/Type, `camelCase` cho hooks/utilities, cấu trúc file `.tsx`.
- **Kent C. Dodds Blog**:
  - Các bài viết kiến trúc nền tảng: _Inversion of Control_, _Compound Components Pattern_, _Colocation of State_, _State Reducer Pattern_.

---

## 3. Thực thi tự động qua Tooling & Linter Rules

Các best practices được tự động hóa và bắt buộc thông qua:

- **ESLint (`eslint-plugin-react-hooks`)**: Bắt buộc tuân thủ Rules of Hooks và kiểm tra Dependency Arrays.
- **TypeScript Compiler (`tsconfig.json`)**:
  - Bật chế độ `"strict": true`.
  - Tránh `any` ngầm (`noImplicitAny`).
  - Kiểm tra null/undefined an toàn (`strictNullChecks`).

---

## 4. Các Best Practices cốt lõi cần nhớ

### A. Component Design & Composition

1. **Single Responsibility**: Mỗi component chỉ nên thực hiện một chức năng duy nhất.
2. **Composition over Inheritance / Flag Bloat**: Sử dụng `children`, Render Props hoặc Compound Components thay vì truyền quá nhiều boolean props (props flag) để điều khiển UI.
3. **Container / Presentational hoặc Server / Client Components**: Tách biệt rõ giữa component xử lý logic/data fetching và component thuần UI.

### B. TypeScript & Typing Rules

1. **Nói không với `any`**: Thay thế bằng `unknown` hoặc generic type khi chưa rõ kiểu dữ liệu.
2. **Sử dụng Discriminated Unions**: Quản lý trạng thái phức tạp (ví dụ: `status: 'idle' | 'loading' | 'success' | 'error'`) để TypeScript tự suy luận payload tương ứng.
3. **Type Props tường minh**: Luôn khai báo `type` hoặc `interface` cho Props của component.

### C. State Management & Hooks

1. **Derive State (State phái sinh)**: Cái gì có thể tính toán trực tiếp từ `props` hoặc `state` hiện có thì **không tạo thêm state mới** và không dùng `useEffect` để đồng bộ.
2. **Co-location**: Đặt state ở component gần nhất sử dụng nó. Khi cần chia sẻ mới lift state up.
3. **Tránh lạm dụng `useEffect`**: Chỉ dùng `useEffect` để đồng bộ với hệ thống bên ngoài (External System: DOM, Websocket, Subscriptions), không dùng cho data transformations hoặc event handling.

### D. File & Project Organization

1. **Co-location Pattern**: Gom nhóm components, types, hooks, styles, tests liên quan đến một tính năng vào cùng một thư mục feature (thay vì gom tất cả types vào 1 thư mục `types/` khổng lồ).
2. **KISS & YAGNI**: Không over-engineering khi dự án chưa thực sự cần sự phức tạp.
