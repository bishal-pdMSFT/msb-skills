---
name: context7
description: Organizes and constrains context by structuring fragmented, dynamic, and cross-source information into stable layers. Use when managing long-chain reasoning, multi-module collaboration, maintaining long-term consistency, or when working with complex projects requiring accumulation, refinement, and reuse of context across tasks. Marks valid information and what should be discarded to maintain cognitive continuity and avoid semantic drift.
---

# Context7

## 概述

Context7 透過將零碎、動態、跨來源的資訊結構化為穩定的層次,來組織和約束上下文。確保分析、規劃和執行都依賴於一致、可追溯的語義環境。

## 核心特性

- **上下文分層**: 將資訊組織為穩定的層次結構
- **語義標記**: 明確標記有效資訊和應捨棄的內容
- **跨任務重用**: 上下文可在多個任務間累積和重用
- **認知連續性**: 維持長期一致性,避免語義漂移
- **動態更新**: 支援上下文的精煉和更新

## 使用時機

當面對以下情況時使用 Context7:

1. **長鏈推理**: 需要多步驟推理且每步依賴前面結果
2. **多模組協作**: 多個模組需要共享上下文資訊
3. **長期專案**: 需要在多次對話間保持一致性
4. **複雜系統**: 涉及多個相互關聯的元件或子系統
5. **知識管理**: 需要累積和重用領域知識

## 上下文層次結構

### 第 0 層: 元資訊 (Meta Layer)

記錄專案基本資訊和全域設定:

```yaml
專案資訊:
  名稱: [專案名稱]
  版本: [版本號]
  開始時間: [日期]
  狀態: [進行中/已完成/暫停]

技術棧:
  框架: Angular 20.3.x
  UI: NG-ZORRO 20.3.1 + NG-ALAIN 20.0.x
  語言: TypeScript 5.9.x
  資料庫: Supabase
  套件管理: yarn

開發環境:
  作業系統: Windows 11
  Node.js: [版本]
  編輯器: [編輯器名稱]
```

### 第 1 層: 領域知識 (Domain Layer)

儲存專案特定的領域知識和業務邏輯:

```yaml
業務實體:
  使用者:
    屬性: [id, name, email, role]
    規則: [驗證規則]
  商品:
    屬性: [id, name, price, stock]
    規則: [業務規則]

業務流程:
  訂單處理:
    步驟:
      1. 驗證商品庫存
      2. 計算總價
      3. 建立訂單
      4. 扣除庫存
    異常處理: [處理方式]
```

### 第 2 層: 架構決策 (Architecture Layer)

記錄重要的技術決策和架構設計:

```yaml
架構決策 ADR-001:
  標題: 使用 NG-ALAIN 作為企業級框架
  狀態: 已採用
  決策日期: 2024-01-15
  
  背景:
    - 需要快速建構企業級後台
    - 需要一致的 UI/UX 體驗
  
  決策:
    - 採用 NG-ALAIN 20.0.x
    - 使用 NG-ZORRO 作為 UI 元件庫
  
  後果:
    - 優點: 開發速度快,元件豐富
    - 缺點: 學習曲線,客製化限制
  
  替代方案:
    - 自建 UI 框架 (被拒絕,開發成本高)
```

### 第 3 層: 實作細節 (Implementation Layer)

記錄具體的實作方式和程式碼結構:

```typescript
模組結構:
  AuthModule:
    路徑: src/app/core/auth/
    元件:
      - LoginComponent: 登入頁面
      - RegisterComponent: 註冊頁面
    服務:
      - AuthService: 認證邏輯
      - TokenService: Token 管理
    守衛:
      - AuthGuard: 路由保護
    
    關鍵實作:
      // 登入流程
      login(email, password) {
        1. 呼叫 Supabase Auth API
        2. 儲存 token 到 localStorage
        3. 更新 BehaviorSubject<User>
        4. 導向儀表板
      }
```

### 第 4 層: 進度追蹤 (Progress Layer)

追蹤開發進度和待辦事項:

```yaml
Sprint 1 (Week 1-2):
  目標: 完成認證模組
  
  已完成:
    - ✓ AuthService 實作
    - ✓ LoginComponent 建立
    - ✓ Supabase 整合
  
  進行中:
    - ⊙ AuthGuard 實作 (80%)
  
  待辦:
    - ☐ 註冊功能
    - ☐ 密碼重設
  
  阻礙:
    - Supabase CORS 設定問題 (已解決)
```

### 第 5 層: 問題與解決方案 (Issues Layer)

記錄遇到的問題和解決方式:

```yaml
問題 #001:
  標題: Angular 20 新控制流語法不熟悉
  狀態: 已解決
  發現日期: 2024-01-10
  
  問題描述:
    - 團隊習慣使用 *ngIf/*ngFor
    - Angular 20 要求使用 @if/@for
  
  解決方案:
    - 學習新語法規範
    - 更新程式碼檢查規則
    - 禁用舊版結構型指令
  
  參考資料:
    - [Angular 20 Control Flow 文件連結]
```

### 第 6 層: 測試與驗證 (Testing Layer)

記錄測試策略和驗證結果:

```yaml
測試策略:
  單元測試:
    覆蓋率目標: 80%
    工具: Jasmine + Karma
    重點:
      - Service 層邏輯
      - Utility 函數
  
  整合測試:
    範圍:
      - AuthModule 與 Supabase 整合
      - 表單驗證流程
  
  E2E 測試:
    工具: Cypress
    關鍵路徑:
      - 登入流程
      - 商品 CRUD

驗證檢查清單:
  AuthModule:
    - ✓ 登入成功後導向正確頁面
    - ✓ 未授權訪問被攔截
    - ✓ Token 過期自動登出
    - ☐ 多裝置登入處理
```

## Angular 專案範例

### 完整的上下文管理範例

```yaml
# ============================================
# 第 0 層: 專案元資訊
# ============================================
專案: ERP 系統重構
版本: 2.0.0
開始日期: 2024-01-01
目標上線: 2024-06-01
狀態: 進行中 (30%)

技術棧:
  前端: Angular 20.3.x + NG-ZORRO + NG-ALAIN
  後端: Supabase (PostgreSQL + Auth + Storage)
  狀態管理: RxJS + BehaviorSubject
  測試: Jasmine + Karma + Cypress

# ============================================
# 第 1 層: 領域知識
# ============================================
核心實體:
  員工 (Employee):
    欄位: id, name, email, department, role, hire_date
    關聯: 屬於一個部門,擁有多個權限
  
  部門 (Department):
    欄位: id, name, manager_id, budget
    關聯: 包含多個員工
  
  假期申請 (LeaveRequest):
    欄位: id, employee_id, start_date, end_date, type, status
    狀態流: 草稿 → 待審核 → 已批准/已拒絕
    規則:
      - 年假不得超過剩餘額度
      - 需提前 3 天申請
      - 主管需在 2 天內審核

# ============================================
# 第 2 層: 架構決策
# ============================================
ADR-001: 採用 NG-ALAIN 框架
  決策: 使用 NG-ALAIN 加速開發
  原因: 內建企業級布局和元件
  影響: 減少 50% 基礎設施開發時間

ADR-002: 狀態管理方案
  決策: 使用 RxJS + Service 模式
  原因: 
    - 不需要 NgRx 的複雜度
    - 與 Angular 整合良好
  替代: NgRx (被拒絕,專案規模不大)

ADR-003: 表單控制流語法
  決策: 統一使用 Angular 20 新語法
  規則:
    - 禁止 *ngIf, 使用 @if
    - 禁止 *ngFor, 使用 @for
    - 禁止 *ngSwitch, 使用 @switch

# ============================================
# 第 3 層: 實作細節
# ============================================
模組結構:
  CoreModule:
    - AuthService
    - EmployeeService
    - DepartmentService
  
  FeaturesModule:
    - EmployeeModule (員工管理)
    - LeaveModule (假期管理)
    - ReportModule (報表分析)
  
  SharedModule:
    - CommonComponents
    - Directives
    - Pipes

假期申請元件實作:
  檔案: leave-request-form.component.ts
  表單欄位:
    - 假期類型 (nz-select)
    - 開始日期 (nz-date-picker)
    - 結束日期 (nz-date-picker)
    - 申請原因 (nz-textarea)
  
  驗證規則:
    - 開始日期不得早於今天
    - 結束日期必須晚於開始日期
    - 年假需檢查剩餘額度
  
  提交流程:
    1. 前端驗證
    2. 呼叫 LeaveService.create()
    3. 顯示成功訊息
    4. 返回列表頁

# ============================================
# 第 4 層: 進度追蹤
# ============================================
Sprint 3 (Week 5-6):
  目標: 完成假期管理模組
  
  已完成 ✓:
    - 假期申請表單
    - 假期列表展示
    - 基本的審核功能
  
  進行中 ⊙:
    - 主管審核介面 (70%)
    - 郵件通知整合 (50%)
  
  待辦 ☐:
    - 假期統計報表
    - 批次審核功能
    - 手機版適配
  
  風險:
    - 郵件服務 API 不穩定
    - 需與 HR 系統整合 (外部依賴)

# ============================================
# 第 5 層: 問題與解決方案
# ============================================
問題 #005:
  標題: NG-ALAIN DatePicker 與 Supabase 日期格式不相容
  狀態: 已解決
  發現: 2024-01-20
  
  問題:
    - DatePicker 回傳 Date 物件
    - Supabase 需要 'YYYY-MM-DD' 字串
    - 時區轉換造成日期偏移
  
  解決方案:
    // 建立統一的日期轉換 Pipe
    @Pipe({ name: 'toSupabaseDate' })
    export class ToSupabaseDatePipe implements PipeTransform {
      transform(date: Date): string {
        return date.toISOString().split('T')[0];
      }
    }
  
  影響模組:
    - LeaveModule
    - ReportModule
  
  相關文件:
    - docs/date-handling.md

問題 #006:
  標題: 表單驗證器無法正確處理非同步驗證
  狀態: 進行中
  發現: 2024-01-22
  
  問題:
    - 年假額度需從後端取得
    - 非同步驗證器觸發時機不對
  
  嘗試方案:
    1. 使用 AsyncValidator (未解決,效能問題)
    2. 改用事件驅動驗證 (測試中)

# ============================================
# 第 6 層: 測試與驗證
# ============================================
測試覆蓋率:
  AuthModule: 85%
  EmployeeModule: 78%
  LeaveModule: 65% (進行中)

關鍵測試案例:
  假期申請流程:
    ✓ TC001: 正常提交假期申請
    ✓ TC002: 超過剩餘額度被拒絕
    ✓ TC003: 日期範圍驗證
    ☐ TC004: 並發提交處理
    ☐ TC005: 網路錯誤重試

驗證檢查清單:
  功能驗證:
    ✓ 員工可查看自己的假期記錄
    ✓ 主管可審核下屬申請
    ☐ 郵件通知正常發送
    ☐ 報表數據正確
  
  非功能驗證:
    ✓ 頁面載入時間 < 2 秒
    ☐ 支援 500+ 並發使用者
    ☐ 符合 WCAG 2.1 無障礙標準
```

## 上下文更新原則

### 標記有效資訊

使用標記系統標示資訊狀態:

```yaml
[VALID] - 當前有效的資訊
[DEPRECATED] - 已過時,但保留參考
[REMOVED] - 已移除,不再使用
[PENDING] - 待確認的資訊
[DRAFT] - 草稿狀態
```

範例:

```yaml
ADR-001: [VALID] 使用 NG-ALAIN
ADR-002: [DEPRECATED] 使用 NgRx (已改用 RxJS)
問題 #003: [REMOVED] IE11 相容性 (不再支援)
功能需求: [PENDING] 多語系支援 (待討論)
```

### 定期精煉

建議每個 Sprint 結束時精煉上下文:

1. 更新進度狀態
2. 標記過時資訊
3. 移除無用內容
4. 補充新的決策和問題
5. 更新測試結果

## 最佳實踐

1. **保持層次分明**: 資訊放在對應的層次中
2. **及時更新**: 有新資訊時立即記錄
3. **明確標記**: 使用狀態標記管理資訊生命週期
4. **避免重複**: 相同資訊不應出現在多個層次
5. **可追溯性**: 記錄決策的原因和時間

## 與其他方法的配合

- **配合 Sequential Thinking**: 將每個思考步驟的結果存入 Context7
- **配合 Software Planning Tool**: 將規劃文件、模組設計存入 Context7
- **跨對話使用**: Context7 的內容可在多次對話中重用
- **團隊協作**: 共享 Context7 文件讓團隊保持同步

## 使用建議

1. **專案初期**: 先建立第 0-2 層的基礎上下文
2. **開發過程**: 持續更新第 3-5 層的實作和問題
3. **測試階段**: 重點維護第 6 層的測試結果
4. **專案交接**: 完整的 Context7 文件即為交接文件
