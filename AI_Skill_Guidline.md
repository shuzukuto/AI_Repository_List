# Sổ Tay Hướng Dẫn Toàn Diện AI Skills (AI Skills Guideline)

> **Tài liệu tổng hợp danh mục, tính năng chi tiết, điều kiện kích hoạt và hướng dẫn sử dụng thực tế của toàn bộ các AI Agent Skills đã cài đặt trong hệ thống.**

## Mục lục

1. [Tổng quan Kiến trúc Hệ sinh thái Skills](#1-t%E1%BB%95ng-quan-ki%E1%BA%BFn-tr%C3%BAc-h%E1%BB%87-sinh-th%C3%A1i-skills)
2. [Nhóm 1: Agent Memory & Session Context Traceability (15 Skills)](#nh%C3%B3m-1-agent-memory--session-context-traceability)
3. [Nhóm 2: CAD, 3D Printing & Robotics Engineering (12 Skills)](#nh%C3%B3m-2-cad-3d-printing--robotics-engineering)
4. [Nhóm 3: Google Data Cloud & GCP Engineering (33 Skills)](#nh%C3%B3m-3-google-data-cloud--gcp-engineering)
5. [Nhóm 4: Agentic Engineering & Superpowers Suite (30 Skills)](#nh%C3%B3m-4-agentic-engineering--superpowers-suite)
6. [Nhóm 5: Google Antigravity Built-in Core Skills (9 Skills)](#nh%C3%B3m-5-google-antigravity-built-in-core-skills)
7. [Nhóm 6: AI Slide Presentation & Deck Generators (2 Skills)](#nh%C3%B3m-6-ai-slide-presentation--deck-generators)
8. [Ma trận Kích hoạt Skill theo Giai đoạn Phát triển (Skill Trigger Matrix)](#ma-tr%E1%BA%ADn-k%C3%ADch-ho%E1%BA%A1t-skill-theo-giai-%C4%91o%E1%BA%A1n-ph%C3%A1t-tri%E1%BB%83n)

---

## 1. Tổng quan Kiến trúc Hệ sinh thái Skills

Hệ sinh thái AI Agent Skills được cấu hình đa tầng theo mô hình mở rộng chuẩn hóa của Google Antigravity. Mỗi skill bao gồm một tệp đặc tả `SKILL.md` (chứa metadata, trigger rules và quy trình hành vi) cùng các tệp kịch bản thực thi, tài liệu tham khảo và mẫu prompt.

| Nhóm kỹ năng | Repository chính thức | Số lượng | Vị trí cài đặt cục bộ |
|---|---|:---:|---|
| **Agent Memory** | [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory) | 15 | `g:/AI_Support/.agents/skills/` |
| **Text-to-CAD & Robotics** | [earthtojake/text-to-cad](https://github.com/earthtojake/text-to-cad) | 12 | `~/.gemini/config/skills/` |
| **Google Data Cloud** | [GoogleCloudPlatform/datacloud-skills](https://github.com/GoogleCloudPlatform/datacloud-skills) | 33 | `~/.gemini/config/skills/` |
| **Superpowers Suite** | [obra/superpowers](https://github.com/obra/superpowers) | 30 | `~/.gemini/config/skills/` & `g:/AI_Support/skills/` |
| **Antigravity Built-in** | [google/antigravity](https://github.com/google/antigravity) | 9 | `~/.gemini/antigravity/builtin/skills/` |
| **Presentation Generators** | [op7418/guizang-ppt-skill](https://github.com/op7418/guizang-ppt-skill) & [hugohe3/ppt-master](https://github.com/hugohe3/ppt-master) | 2 | `~/.gemini/config/skills/` |
| **TỔNG CỘNG** | **Hệ sinh thái 6 nguồn** | **101** | *Toàn bộ hệ thống máy chủ phát triển* |

---

## 1. Nhóm Agent Memory & Session Context Traceability

- **Repository nguồn**: [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory)
- **Mô tả nhóm**: Bộ kỹ năng quản lý bộ nhớ dài hạn, lưu vết ngữ cảnh phiên làm việc, kết nối MCP và truy vết lịch sử Git với Agent sessions.
- **Số lượng kỹ năng**: **15 skills**

### `agentmemory-agents`
> **Mã định danh**: `agentmemory-agents` | **Repository**: [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory)

- **Tính năng chính**:
  Tự động tích hợp agentmemory vào các coding agent thông qua lệnh `connect`. Cung cấp adapter tương thích cho Claude Code, Gemini CLI, Cursor, Windsurf, Roo Code, Goose, và Codex.
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi cài đặt agentmemory vào một agent cụ thể, giải thích agent nào được hỗ trợ hoặc khi adapter ghi sai đường dẫn cấu hình.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy kiểm tra cấu hình kết nối của agentmemory với agent hiện tại và khắc phục lỗi nếu đường dẫn adapter bị sai.
  ```

### `agentmemory-architecture`
> **Mã định danh**: `agentmemory-architecture` | **Repository**: [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory)

- **Tính năng chính**:
  Mô tả kiến trúc nền tảng của agentmemory, các primitive của iii engine, mô hình lưu trữ phân tán, cổng mạng và giao diện xem trực quan (Viewer).
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi cần phân tích luồng lưu và truy xuất ký ức từ đầu đến cuối, mở rộng hệ thống hoặc giải thích cơ chế bên dưới.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Giải thích kiến trúc lưu trữ của agentmemory và cách các memory observation được đồng bộ vào iii engine.
  ```

### `agentmemory-config`
> **Mã định danh**: `agentmemory-config` | **Repository**: [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory)

- **Tính năng chính**:
  Quản lý biến môi trường, cấu hình cổng (ports), feature flags, xác thực và cấu hình bảo mật cho memory server.
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi bật/tắt tính năng, đổi port mặc định, cấu hình API key hoặc kiểm tra vì sao một flag bị tắt theo mặc định.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hướng dẫn cấu hình cổng mạng và biến môi trường cho memory server chạy trên localhost.
  ```

### `agentmemory-hooks`
> **Mã định danh**: `agentmemory-hooks` | **Repository**: [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory)

- **Tính năng chính**:
  Cung cấp hệ thống hooks tự động thu thập các observation xuyên suốt vòng đời session (khởi động, trước tool call, sau tool call, kết thúc session).
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi cần cơ chế ghi nhớ tự động không cần người dùng ra lệnh thủ công, hoặc gỡ lỗi tại sao observation không được ghi nhận.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Cấu hình lifecycle hooks để tự động lưu lại các quyết định kiến trúc quan trọng vào agentmemory mỗi khi kết thúc task.
  ```

### `agentmemory-mcp-tools`
> **Mã định danh**: `agentmemory-mcp-tools` | **Repository**: [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory)

- **Tính năng chính**:
  Bản đồ tra cứu toàn bộ các công cụ MCP do agentmemory cung cấp (save_observation, search_memory, trace_session, get_context, etc.).
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi chọn tool MCP phù hợp, làm rõ tham số đầu vào/đầu ra của tool hoặc kiểm tra khả năng tích hợp qua MCP.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Liệt kê các MCP tools có sẵn của agentmemory và cú pháp gọi tool tìm kiếm ngữ cảnh.
  ```

### `agentmemory-rest-api`
> **Mã định danh**: `agentmemory-rest-api` | **Repository**: [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory)

- **Tính năng chính**:
  Đặc tả toàn bộ bề mặt HTTP REST API của memory server; đóng vai trò là giao thức chính để giao tiếp khi MCP không khả dụng.
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi gọi agentmemory qua HTTP từ terminal/cURL, khi MCP server bị lỗi hoặc tích hợp agent không hỗ trợ MCP.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Viết mã Python gửi request HTTP REST API tới agentmemory endpoint để truy xuất ký ức gần nhất.
  ```

### `commit-context`
> **Mã định danh**: `commit-context` | **Repository**: [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory)

- **Tính năng chính**:
  Truy vết ngược dòng một tệp, một hàm hoặc một dòng mã cụ thể về đúng agent session đã sinh ra commit hiện tại.
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi đặt câu hỏi: 'Tại sao đoạn code này lại ở đây?', 'Agent đang làm gì khi commit này sinh ra?', 'Ai đã viết đoạn này?'.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy truy vết commit gần nhất trên file nas_app/main.py để xem session của agent nào đã thực hiện thay đổi đó.
  ```

### `commit-history`
> **Mã định danh**: `commit-history` | **Repository**: [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory)

- **Tính năng chính**:
  Liệt kê các git commits gần nhất có liên kết chặt chẽ với các agent sessions, hỗ trợ lọc theo branch hoặc repository.
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi cần kiểm tra: 'Những commit nào do agent thực hiện gần đây?', 'Tổng kết các thay đổi agent đã đưa lên repo'.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hiển thị lịch sử các git commit gần nhất được liên kết với agent session trên nhánh hiện tại.
  ```

### `forget`
> **Mã định danh**: `forget` | **Repository**: [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory)

- **Tính năng chính**:
  Xóa bỏ các observation cụ thể khỏi bộ nhớ agentmemory sau khi hiển thị chi tiết cho người dùng và nhận được xác nhận tường minh.
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi người dùng yêu cầu: 'quên cái này đi', 'xóa ký ức', 'bỏ ghi chú đó', hoặc cần thanh lọc thông tin nhạy cảm.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy tìm và xóa observation liên quan đến khóa API thử nghiệm trong agentmemory sau khi tôi xác nhận.
  ```

### `handoff`
> **Mã định danh**: `handoff` | **Repository**: [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory)

- **Tính năng chính**:
  Bàn giao phiên làm việc liền mạch: Khôi phục lại session gần nhất của thư mục làm việc hiện tại, bắt đầu bằng các câu hỏi/task chưa có lời giải.
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi người dùng yêu cầu: 'chúng ta đang dừng ở đâu', 'tiếp tục công việc', 'handoff', 'nối lại phiên trước'.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Chúng ta đang dừng ở đâu trong phiên làm việc trước? Hãy tóm tắt và tiếp tục các bước còn dở dang.
  ```

### `recall`
> **Mã định danh**: `recall` | **Repository**: [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory)

- **Tính năng chính**:
  Tìm kiếm ký ức lai (Hybrid Search) kết hợp BM25 (từ khóa) + Vector Search (ngữ nghĩa) + Graph Search (quan hệ thực thể).
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi người dùng hỏi: 'nhớ lại xem', 'lần trước đã làm gì với module X', 'trước đây có gặp lỗi này chưa'.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy tìm lại trong ký ức xem chúng ta đã thống nhất quy tắc đặt tên bảng CSDL như thế nào ở các phiên trước.
  ```

### `recap`
> **Mã định danh**: `recap` | **Repository**: [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory)

- **Tính năng chính**:
  Tổng hợp và tóm tắt N phiên làm việc gần nhất cho dự án hiện tại, gom nhóm theo ngày và nêu bật các quan sát quan trọng.
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi người dùng hỏi: 'recap', 'hôm nay đã làm được gì', 'tuần này đã thay đổi những gì', 'báo cáo tổng kết'.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Tóm tắt lại các phiên làm việc của ngày hôm nay và những đầu việc chính đã được giải quyết.
  ```

### `remember`
> **Mã định danh**: `remember` | **Repository**: [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory)

- **Tính năng chính**:
  Lưu các hiểu biết sâu sắc (insights), quyết định kiến trúc hoặc bài học kinh nghiệm vào bộ nhớ dài hạn kèm thẻ khái niệm (tags).
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi người dùng yêu cầu: 'ghi nhớ điều này', 'lưu lại cái này', 'note lại đừng quên', hoặc cần bảo toàn kiến thức cho tương lai.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy ghi nhớ vào bộ nhớ dài hạn: Mọi truy vấn SQLite trong dự án bắt buộc phải đi qua nas_app/main.py.
  ```

### `session-history`
> **Mã định danh**: `session-history` | **Repository**: [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory)

- **Tính năng chính**:
  Hiển thị dòng thời gian trực quan về những gì đã diễn ra trong các session quá khứ của dự án hiện tại.
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi người dùng muốn xem lại tiến trình công việc, các sự kiện quan trọng trong các phiên trước theo thứ tự thời gian.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hiển thị dòng thời gian các sự kiện và quyết định chính trong 3 session gần nhất.
  ```

### `write-agentmemory-skill`
> **Mã định danh**: `write-agentmemory-skill` | **Repository**: [rohitg00/agentmemory](https://github.com/rohitg00/agentmemory)

- **Tính năng chính**:
  Hướng dẫn định dạng chuẩn và bộ quy tắc khi viết hoặc cập nhật một skill mới thuộc hệ sinh thái agentmemory.
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi thêm skill mới, tái cấu trúc skill hiện có hoặc review đóng góp kỹ năng của cộng đồng.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Tạo một skill mới tuân thủ đầy đủ chuẩn viết của agentmemory với frontmatter và file REFERENCE.md đi kèm.
  ```

---

## 2. Nhóm CAD, 3D Printing & Robotics Engineering

- **Repository nguồn**: [earthtojake/text-to-cad](https://github.com/earthtojake/text-to-cad)
- **Mô tả nhóm**: Bộ kỹ năng kỹ thuật cơ khí số hóa, thiết kế CAD tham số (Python build123d), cắt lát in 3D (OrcaSlicer/Bambu), bản vẽ kỹ thuật 2D DXF/PDF và mô hình hóa Robot (URDF/SRDF/SDF).
- **Số lượng kỹ năng**: **12 skills**

### `bambu-labs`
> **Mã định danh**: `bambu-labs` | **Repository**: [earthtojake/text-to-cad](https://github.com/earthtojake/text-to-cad)

- **Tính năng chính**:
  Tự động kết nối và gửi lệnh in tới máy in Bambu Lab thông qua Bambu Connect hoặc Bambu Studio (qua Cloud hoặc LAN).
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi người dùng muốn in file `.gcode.3mf`, file `.gcode` hoặc mô hình 3D chưa slice lên máy in Bambu Lab.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Gửi tệp mô hình 3D vừa thiết kế sang ứng dụng Bambu Connect để bắt đầu lệnh in trên máy Bambu X1-Carbon.
  ```

### `cad`
> **Mã định danh**: `cad` | **Repository**: [earthtojake/text-to-cad](https://github.com/earthtojake/text-to-cad)

- **Tính năng chính**:
  Lập trình thiết kế mô hình CAD tham số 3D bằng Python (thư viện build123d), xuất định dạng STEP, STL, 3MF, GLB và đo đạc hình học bằng cadgen.
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi người dùng muốn tạo chi tiết 3D chính xác bằng code, sửa đổi thông số hình học hoặc kiểm tra mô hình trong CAD Viewer.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy viết mã Python build123d để tạo mô hình vỏ hộp bảo vệ Raspberry Pi có lỗ thông gió và xuất ra file STEP.
  ```

### `dfam-check`
> **Mã định danh**: `dfam-check` | **Repository**: [earthtojake/text-to-cad](https://github.com/earthtojake/text-to-cad)

- **Tính năng chính**:
  Kiểm tra mô hình lưới (mesh) theo các quy tắc Thiết kế cho Sản xuất Bồi đắp (DfAM) cho các công nghệ FDM, SLS, SLA/DLP, Metal PBF.
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi cần kiểm tra độ dày thành tối thiểu, góc nghiêng tự nâng đỡ (overhangs), hướng in tối ưu trước khi cắt lát.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Phân tích file part.stl xem có vùng nào thành quá mỏng hoặc góc nghiêng cần support khi in công nghệ FDM không.
  ```

### `dfm`
> **Mã định danh**: `dfm` | **Repository**: [earthtojake/text-to-cad](https://github.com/earthtojake/text-to-cad)

- **Tính năng chính**:
  Đánh giá thiết kế hướng đến chế tạo (DFM) cho gia công kim loại tấm (sheet metal), phay tiện CNC hoặc đúc ép nhựa (injection molding).
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi đánh giá bán kính uốn cong, góc vát thoát khuôn (draft angle), góc lượn trong và khả năng gia công trên máy công cụ.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Đánh giá DFM cho chi tiết cơ khí này xem có gia công được trên máy phay CNC 3 trục hay không.
  ```

### `dxf`
> **Mã định danh**: `dxf` | **Repository**: [earthtojake/text-to-cad](https://github.com/earthtojake/text-to-cad)

- **Tính năng chính**:
  Sinh, tái tạo và kiểm tra tính hợp lệ của bản vẽ kỹ thuật 2D định dạng DXF từ mã nguồn Python build123d (cho cắt laser, plasma, waterjet).
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi cần tạo file cắt 2D, biên dạng mặt bích, gioăng đệm, tấm kim loại phẳng hoặc layout trải phôi.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Tạo bản vẽ 2D định dạng DXF cho mặt bích lắp ghép có 4 lỗ bu lông M6 cách tâm 50mm để cắt laser.
  ```

### `engineering-drawing`
> **Mã định danh**: `engineering-drawing` | **Repository**: [earthtojake/text-to-cad](https://github.com/earthtojake/text-to-cad)

- **Tính năng chính**:
  Tạo bản vẽ chế tạo kỹ thuật 2D xuất ra file PDF theo tiêu chuẩn ISO: Bao gồm các hình chiếu trực giao, hình cắt, đường tâm, kích thước và khung tên.
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi người dùng yêu cầu: 'tạo bản vẽ chế tạo', 'xuất bản vẽ PDF có kích thước', 'bản vẽ phân xưởng'.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Xuất bản vẽ kỹ thuật 2D chuẩn khổ giấy A3 định dạng PDF từ mô hình 3D, đầy đủ 3 hình chiếu và kích thước tổng thể.
  ```

### `gcode`
> **Mã định danh**: `gcode` | **Repository**: [earthtojake/text-to-cad](https://github.com/earthtojake/text-to-cad)

- **Tính năng chính**:
  Cắt lát mô hình 3D (Slicing) sang G-code sẵn sàng in thông qua giao diện dòng lệnh không đầu (headless CLI) của OrcaSlicer.
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi cần tạo file `.gcode.3mf` hoặc `.gcode` cho máy in Prusa, Bambu Lab, Creality, Voron từ tệp STL/OBJ/3MF.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Cắt lát file bracket.stl bằng OrcaSlicer với profile máy Voron 2.4, vật liệu ABS, layer 0.2mm, infill 40%.
  ```

### `sdf`
> **Mã định danh**: `sdf` | **Repository**: [earthtojake/text-to-cad](https://github.com/earthtojake/text-to-cad)

- **Tính năng chính**:
  Soạn thảo, kiểm tra và bàn giao mô hình định dạng SDFormat (SDF) cho môi trường mô phỏng Gazebo (links, joints, visual/collision, physics).
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi xây dựng robot hoặc môi trường mô phỏng vật lý đa vật thể trong Gazebo Simulator.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Tạo tệp mô hình SDF mô tả xe tự hành 2 bánh vi sai có gắn cảm biến Lidar trên nóc để mô phỏng trong Gazebo.
  ```

### `sendcutsend`
> **Mã định danh**: `sendcutsend` | **Repository**: [earthtojake/text-to-cad](https://github.com/earthtojake/text-to-cad)

- **Tính năng chính**:
  Kiểm tra trước khi đặt hàng (preflight) cho các tệp DXF và STEP tải lên nền tảng gia công trực tuyến SendCutSend.com.
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi cần đối chiếu dung sai cắt laser, uốn cong kim loại, taro ren, vát mép với danh mục vật liệu và khả năng gia công thực tế.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Kiểm tra file bracket.dxf xem đã đạt tiêu chuẩn cắt laser thép không gỉ dày 3mm trên dịch vụ SendCutSend chưa.
  ```

### `srdf`
> **Mã định danh**: `srdf` | **Repository**: [earthtojake/text-to-cad](https://github.com/earthtojake/text-to-cad)

- **Tính năng chính**:
  Soạn thảo, xác thực và cấu hình ngữ nghĩa lập kế hoạch chuyển động cho MoveIt2: Cấu hình planning groups, end effectors, disabled collision pairs.
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi tích hợp cánh tay robot với ROS2/MoveIt2 để hoạch định quỹ đạo chuyển động không va chạm.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Tạo file cấu hình SRDF định nghĩa planning group 'arm' và tắt kiểm tra va chạm giữa các khớp liền kề cho cánh tay robot 6 bậc tự do.
  ```

### `step-parts`
> **Mã định danh**: `step-parts` | **Repository**: [earthtojake/text-to-cad](https://github.com/earthtojake/text-to-cad)

- **Tính năng chính**:
  Tìm kiếm, đánh giá và tải về các linh kiện tiêu chuẩn mua sẵn từ catalog trực tuyến step.parts (vít, đai ốc, vòng bi, động cơ, cảm biến).
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi cần lắp ghép linh kiện thương mại vào mô hình CAD thay vì vẽ lại hình học từ đầu.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Tìm và tải mô hình STEP chuẩn của vòng bi 608ZZ và động cơ bước NEMA 17 từ catalog step.parts.
  ```

### `urdf`
> **Mã định danh**: `urdf` | **Repository**: [earthtojake/text-to-cad](https://github.com/earthtojake/text-to-cad)

- **Tính năng chính**:
  Xây dựng, chỉnh sửa, kiểm tra và gỡ lỗi tệp mô tả cấu trúc robot Unified Robot Description Format (URDF) trong hệ sinh thái ROS/ROS2.
- **Điều kiện kích hoạt (When to use)**:
  Dùng khi định nghĩa động học robot: Khung liên kết (links), khớp xoay/tịnh tiến (joints), ma trận quán tính (inertia) và hình học va chạm.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Viết tệp URDF hoàn chỉnh mô tả cánh tay robot Scara 3 bậc tự do có đầy đủ ma trận quán tính và giới hạn góc quay.
  ```

---

## 3. Nhóm Google Data Cloud & GCP Engineering Skills

- **Repository nguồn**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)
- **Mô tả nhóm**: Bộ kỹ năng tiêu chuẩn doanh nghiệp cho kỹ thuật dữ liệu đám mây: BigQuery, Dataflow, Cloud Composer (Airflow), Dataproc (Spark), Cloud Storage, dbt, Dataform, và bảo mật dữ liệu.
- **Số lượng kỹ năng**: **33 skills**

### `accidental-data-loss-prevention`
> **Mã định danh**: `accidental-data-loss-prevention` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  **STOP AND VERIFY**: Before running any command or tool that results in irreversible data loss, you MUST obtain explicit user consent. When in doubt, ask. It is better to wait for confirmation than to accidentally delete production data or critical project assets. Use this for: - SQL: DROP TABLE/VIEW/SCHEMA/DATABASE, TRUNCATE, or broad DELETE (missing WHERE or using 1=1). - Cloud Storage: gsutil rm or gcloud storage rm targeting production data or critical buckets. - Infrastructure: gcloud projects delete, deleting Spanner/BigQuery/Dataproc resources, deleting secrets, or KMS key destruction.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `accidental-data-loss-prevention` để phân tích và thực hiện tác vụ này.
  ```

### `bigquery-ai-ml`
> **Mã định danh**: `bigquery-ai-ml` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Leverages BigQuery's built-in machine learning and GenAI capabilities for advanced data analytics. Use when you need to write SQL queries that perform time-series forecasting, detect outliers, find key drivers, or leverage generative AI capabilities in BigQuery.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `bigquery-ai-ml` để phân tích và thực hiện tác vụ này.
  ```

### `bigquery-bigframes`
> **Mã định danh**: `bigquery-bigframes` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Generates Python code using BigQuery DataFrames (BigFrames), the pandas/scikit-learn-style\ \ API over BigQuery. Use when writing BigFrames code or doing pandas-style dataframe/ML\ \ work against BigQuery (e.g. in a notebook). Don't use for SQL-first workflows\ \ or the google-cloud-bigquery client library \u2014 use bigquery-basics.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `bigquery-bigframes` để phân tích và thực hiện tác vụ này.
  ```

### `bigquery-data-transfer-service`
> **Mã định danh**: `bigquery-data-transfer-service` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Discovers and inspects BigQuery Data Transfer Service (DTS) configurations. Use this to identify existing ingestion pipelines and extract datasource or transfer config metadata for data pipelines. Use when a user asks for ingestion scenarios while building or managing data pipelines or when a user asks to "ingest" or "add" data that may already be managed by a DTS transfer.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `bigquery-data-transfer-service` để phân tích và thực hiện tác vụ này.
  ```

### `bigquery-graph`
> **Mã định danh**: `bigquery-graph` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Provides guidelines and best practices for querying and defining property graphs and semantic graphs in BigQuery using GQL (Graph Query Language). Use when creating property graphs or querying graph topologies in BigQuery.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `bigquery-graph` để phân tích và thực hiện tác vụ này.
  ```

### `bigquery-sql`
> **Mã định danh**: `bigquery-sql` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Provides BigQuery SQL query optimization techniques, execution best practices, and performance tuning rules for high-efficiency querying. Use when optimizing BigQuery SQL queries, reducing query costs, or designing performant SQL transformations.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `bigquery-sql` để phân tích và thực hiện tác vụ này.
  ```

### `bigtable-basics`
> **Mã định danh**: `bigtable-basics` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Assists in provisioning instances/tables, designing performant schemas, and querying data in Bigtable. Use when designing Bigtable row keys, configuring column families, writing SQL queries or client library code (Java, Go, Python) for Bigtable, or diagnosing performance/hotspotting issues. Also use when provisioning Bigtable clusters using gcloud or cbt CLIs. Don't use for generic Cloud SQL administration.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `bigtable-basics` để phân tích và thực hiện tác vụ này.
  ```

### `building-data-apps`
> **Mã định danh**: `building-data-apps` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Build modern data apps, dashboards, and interactive reports using either React + Vite or Streamlit. Includes optional Gemini Data Analytics chat integration for an AI powered "chat with your data" experience. Relevant when any of the following conditions are true: 1. User explicitly requests to build a data dashboard, data application, or visualization UI, and the UI pulls data from a GCP database (defaulting to BigQuery unless otherwise specified). 2. You need to generate a frontend web application to interact with, query, and visualize data from GCP data sources. 3. User wants to build a "chat with your data" experience or integrate the Gemini Data Analytics chat API into a web interface. Do NOT use when any of the following conditions are true: 1. The request is for building backend-only services. 2. The request is for simple CLI scripts or command-line applications. 3. The web application is not data-centric or does not involve visualizing/querying data from GCP sources.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `building-data-apps` để phân tích và thực hiện tác vụ này.
  ```

### `data-autocleaning`
> **Mã định danh**: `data-autocleaning` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Automated data quality and transformation capabilities for Dataform/dbt/BigQuery pipelines. Processes data sourced from BigQuery or Cloud Storage (GCS), applying best practices for data ingestion, movement, schema mapping, and comprehensive data cleaning.
- **Điều kiện kích hoạt (When to use)**:
  Apply to **all operations** on new and existing sources: copying, moving, Apply to the **source node** specifically, not to subsequent pipeline steps. **Never skip** Dataplex profiling (Steps 1 and 3). Always use Dataplex —
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `data-autocleaning` để phân tích và thực hiện tác vụ này.
  ```

### `dataform-bigquery`
> **Mã định danh**: `dataform-bigquery` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Expertise in generating clean, correct, and efficient Dataform pipeline code for BigQuery ELT. Use this when creating or modifying Dataform pipelines, actions, or source declarations, when Dataform, SQLX, or BigQuery are mentioned in a transformation, when data needs to be ingested from GCS into BigQuery via Dataform, or when setting up a new Dataform project or configuring workflow_settings.yaml.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `dataform-bigquery` để phân tích và thực hiện tác vụ này.
  ```

### `dbt-bigquery`
> **Mã định danh**: `dbt-bigquery` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Expert guidance for creating, modifying, and optimizing dbt pipelines for BigQuery. Use this skill whenever user asks for generating or modifying a dbt model or project. Activate this skill when the user - Creates, modifies, or troubleshoots **dbt models or pipelines** - Needs to **optimize SQL** within a dbt project - Is **setting up a new dbt project** or configuring existing one
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `dbt-bigquery` để phân tích và thực hiện tác vụ này.
  ```

### `discovering-gcp-data-assets`
> **Mã định danh**: `discovering-gcp-data-assets` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Finds and inspects data assets within Google Cloud. Relevant when any of the following conditions are true: 1. The user request involves finding, exploring, or inspecting data assets in Google Cloud, such as: - BigQuery datasets, tables, or views - BigLake catalog or tables - Spanner instances, databases or tables - etc. 2. You need to retrieve the schema, metadata, or governance policies for a GCP data asset. 3. You have a keyword or topic (e.g., "sales data") but lack the specific table or resource ID. 4. You are attempting to find data using `bq ls`, as this skill offers a superior approach. Don't use when: - Assets are outside Google Cloud
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `discovering-gcp-data-assets` để phân tích và thực hiện tác vụ này.
  ```

### `enforcing-resource-attribution`
> **Mã định danh**: `enforcing-resource-attribution` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Enforces resource attribution for CLI commands. Use this skill whenever you are running `bq` or `gcloud` commands via `run_command`. It ensures mandatory labeling for supported `bq` operations while avoiding invalid flags on read-only commands. 
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `enforcing-resource-attribution` để phân tích và thực hiện tác vụ này.
  ```

### `federate-lakehouse-catalog`
> **Mã định danh**: `federate-lakehouse-catalog` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Sets up Google Cloud Lakehouse federated catalogs to remote Iceberg REST Catalogs. Currently supported catalogs: Databricks Unity, AWS Glue. Supported clouds hosting those catalogs: GCP, AWS. The primary use case is connecting to remote data to query it from GCP engines (BigQuery, Spark). Examples of when to use this: "federate my lakehouse catalog to databricks", "query data in databricks", "query data in s3", "connect to aws glue". Do NOT use for direct remote database SQL execution (e.g., Databricks SQL) or managing remote clusters and infrastructure (e.g., Databricks clusters, AWS Glue jobs).
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `federate-lakehouse-catalog` để phân tích và thực hiện tác vụ này.
  ```

### `gcp-composer-troubleshooting`
> **Mã định danh**: `gcp-composer-troubleshooting` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Provides expert guidance for troubleshooting Cloud Composer (Apache Airflow) and Orchestration pipelines. Use this skill when the user asks to generate Root Cause Analysis (RCA), troubleshoot or fix a failed pipeline, DAG in Composer environment and generate RCA report. 
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `gcp-composer-troubleshooting` để phân tích và thực hiện tác vụ này.
  ```

### `gcp-data-pipelines`
> **Mã định danh**: `gcp-data-pipelines` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Primary entry point for building, managing, and orchestrating data pipelines on Google Cloud. Guides users to the appropriate skill for dbt, Dataflow (Apache Beam), Dataform, Spark (Dataproc Serverless), BigQuery Data Transfer Service (DTS) or orchestration pipeline using Cloud Composer. Clarify requirements and resolve ambiguity for creating, updating and running data pipelines. 
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `gcp-data-pipelines` để phân tích và thực hiện tác vụ này.
  ```

### `gcp-dataflow`
> **Mã định danh**: `gcp-dataflow` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Guides writing, packaging, executing, and troubleshooting Apache Beam pipelines on Dataflow. Use when creating new pipelines, configuring Flex Templates, or analyzing performance of Dataflow jobs. Capabilities include Java/Python/Go setup, Cloud Build integration, and deep diagnostic analysis of job health and autoscaling. Use when: - Creating an Apache Beam Dataflow pipeline. - Creating a Google Dataflow Flex Template. - Using an existing Google Dataflow Template. - Debugging Dataflow pipeline - Troubleshooting Dataflow pipeline - Analyzing Performance of Dataflow pipeline. Key capabilities: Java/Python/Go project setup, Flex Templates (with Cloud Build), and diagnostics for streaming job health, bottlenecks, and autoscaling. Do NOT use for: - General GCP resource management unrelated to Dataflow. - Issues with other GCP services (e.g., GCE, GCS, BigQuery) unless directly impacting Dataflow pipeline execution. - Pipeline technologies other than Apache Beam on Dataflow.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `gcp-dataflow` để phân tích và thực hiện tác vụ này.
  ```

### `gcp-managed-airflow-dag-authoring`
> **Mã định danh**: `gcp-managed-airflow-dag-authoring` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Guides the authoring and validation of Apache Airflow DAGs for Managed Service for Apache Airflow (MSAA; formerly Cloud Composer). Covers environment context discovery, Airflow 2 vs 3 compatibility, authoring best practices, and local/remote validation processes. Use when creating or extending an Airflow DAG. Don't use when authoring Python code unrelated to Airflow DAGs.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `gcp-managed-airflow-dag-authoring` để phân tích và thực hiện tác vụ này.
  ```

### `gcp-managed-airflow-migrations`
> **Mã định danh**: `gcp-managed-airflow-migrations` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Provides guidance for migrating Apache Airflow DAGs in Managed Service for Apache Airflow (MSAA; formerly Cloud Composer). Covers migration to Airflow 2.11.1 (MSAA Gen 2 and 3) and Airflow 3 (MSAA Gen 3), including environment inspection, GCS download/upload and scanning patterns for breaking changes.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `gcp-managed-airflow-migrations` để phân tích và thực hiện tác vụ này.
  ```

### `gcp-managed-airflow-recommendations`
> **Mã định danh**: `gcp-managed-airflow-recommendations` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Provides recommendations and best practices for creating, configuring, tuning and optimizing Managed Service for Apache Airflow (MSAA, Cloud Composer) environments. Use when the user asks for guidance, recommendations, or best practices on configuring Cloud Composer, scaling Airflow environments, preventing workload restarts, or analyzing system health.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `gcp-managed-airflow-recommendations` để phân tích và thực hiện tác vụ này.
  ```

### `gcp-pipeline-orchestration`
> **Mã định danh**: `gcp-pipeline-orchestration` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  This skill helps the agent generate or update orchestration pipeline definitions for Google Cloud Composer to initialize orchestration pipeline or update the orchestration definition for orchestration of various data pipelines, like dbt pipelines, notebooks, Spark jobs, Dataform, Python scripts or inline BigQuery SQL queries. This skill also helps deploy and trigger orchestration pipelines.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `gcp-pipeline-orchestration` để phân tích và thực hiện tác vụ này.
  ```

### `gcp-pipeline-resource-provisioning`
> **Mã định danh**: `gcp-pipeline-resource-provisioning` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Automates declarative resource creation and provisioning for data pipelines, supporting BigQuery, Dataform, Dataproc, BigQuery Data Transfer Service (DTS), and other resources. It manages environment-specific configurations (dev, staging, prod) through a deployment.yaml file. Use when: - Modifying or creating deployment.yaml for deployment settings. - Resolving environment-specific variables (e.g., Project IDs, Regions) for deployment. - Provisioning supported infrastructure like BigQuery datasets/tables, Dataform resources, or DTS resources via deployment.yaml. Do not use when: - Resources already exist. - Managing resources not supported by `gcloud beta orchestration-pipelines resource-types list`. - Managing general cloud infrastructure (VMs, networks, Kubernetes, IAM policies), which are better suited for Terraform. - Infrastructure spans multiple cloud providers (AWS, Azure, etc.). - Already uses Terraform for the target resources.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `gcp-pipeline-resource-provisioning` để phân tích và thực hiện tác vụ này.
  ```

### `gcp-spark`
> **Mã định danh**: `gcp-spark` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Develops and executes Spark code on Managed Spark on Google Cloud (Dataproc Clusters and Serverless). Reads and writes data using BigLake Iceberg catalogs, BigQuery and Spanner. Debugs execution failures. Use when: - Writing Spark ETL pipelines on Google Cloud Platform. - Training or running inference with Machine Learning models with spark on Google Cloud Platform. - Managing Spark clusters, jobs, batches, and interactive sessions. Don't use when: - Writing generic Python scripts that don't use Spark. - Performing simple SQL queries that can be done directly in BigQuery.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `gcp-spark` để phân tích và thực hiện tác vụ này.
  ```

### `gcs-security-assessment`
> **Mã định danh**: `gcs-security-assessment` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Assesses the security posture of Google Cloud Storage (GCS) buckets\ \ and projects. Grounds every finding in gathered telemetry, evaluates buckets against\ \ Google security best practices (public access, IAM over-granting, CMEK, VPC Service\ \ Controls, audit logging), and correlates signals to flag toxic combinations of\ \ individually low-risk settings, with actionable remediation. Use whenever a user\ \ asks for a security scan, audit, review, vulnerability check, or compliance assessment\ \ (including SAIF) \u2014 or simply asks whether their buckets, project, or data\ \ are secure, exposed, public, or misconfigured, who can access their data, or wants\ \ storage hardened or locked down, e.g. before a launch. Don't use for diagnosing\ \ a specific access failure or 403, managing or configuring storage, investigating\ \ a live outage, or non-GCS resources (Compute Engine, GKE, etc.).
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `gcs-security-assessment` để phân tích và thực hiện tác vụ này.
  ```

### `google-cloud-auth-verification`
> **Mã định danh**: `google-cloud-auth-verification` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Mandatory Step 0 pre-flight execution order and authentication verification for Google Cloud Platform (GCP), Application Default Credentials (ADC), gcloud CLI, Spark, Dataproc, BigQuery, GCS, and notebook runtimes. Use whenever interacting with GCP resources, running Spark/PySpark pipelines, BigQuery queries, GCS paths (gs://), or creating/running notebooks.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `google-cloud-auth-verification` để phân tích và thực hiện tác vụ này.
  ```

### `google-cloud-storage-basics`
> **Mã định danh**: `google-cloud-storage-basics` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Stores, retrieves, and manages data as objects in Cloud Storage (Google\ \ Cloud Storage, or GCS) buckets. Use when you need to interact with Cloud Storage\ \ \u2014 create or configure buckets, upload, download, stream, or transfer data,\ \ organize objects with folders, generate signed URLs, control access (IAM, ACLs,\ \ public access prevention), set storage classes and tiering (Standard, Nearline,\ \ Coldline, Archive), manage cost and lifecycle, protect data (versioning, encryption/CMEK,\ \ retention and Bucket Lock, object holds, soft delete), host static websites, trigger\ \ Pub/Sub notifications on object changes, mount buckets as a file system (gcsfuse),\ \ or optimize storage performance at any scale. Covers the gcloud storage / gsutil\ \ CLI, JSON and XML APIs, client libraries, Terraform, and Cloud Storage MCP servers.\ \ Don't use for block storage (Persistent Disk), data warehousing/analytics (BigQuery),\ \ or databases (Cloud SQL, Spanner, Bigtable, Firestore).
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `google-cloud-storage-basics` để phân tích và thực hiện tác vụ này.
  ```

### `google-cloud-storage-bucket-architect`
> **Mã định danh**: `google-cloud-storage-bucket-architect` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Creates Cloud Storage (Google Cloud Storage, or GCS) buckets. Analyzes\ \ the workload (sensitive data, media hosting, ingestion, web hosting, archiving,\ \ backup, logging, analytics, AI/ML, or general-purpose), validates project-level\ \ security settings, and designs a secure-by-default, cost-effective configuration\ \ (location, storage class, uniform bucket-level access, public access prevention,\ \ soft delete, lifecycle) before creating it. Use whenever a user wants to create,\ \ make, set up, provision, or spin up a bucket, or needs object storage for an app,\ \ service, pipeline, or dataset \u2014 even a \"simple\" or \"default\" bucket,\ \ or when bucket creation is one step in a larger workflow. Outputs or executes\ \ the creation via gcloud, the JSON/REST API, Terraform, or SDK client libraries\ \ (C++, Java, Python, Go). Don't use for anything other than creating new buckets\ \ \u2014 for uploads, downloads, access changes, or reconfiguring existing buckets,\ \ use google-cloud-storage-basics.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `google-cloud-storage-bucket-architect` để phân tích và thực hiện tác vụ này.
  ```

### `google-cloud-storage-fuse`
> **Mã định danh**: `google-cloud-storage-fuse` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Mounts Cloud Storage buckets as a POSIX file system with Cloud Storage\ \ FUSE (gcsfuse). Use when you need to interact with gcsfuse \u2014 decide whether\ \ FUSE, native gs:// reads, or Filestore/Managed Lustre fits a workload, deploy\ \ tuned mounts on GKE, Compute Engine, or Cloud Run, enable and size the file, stat,\ \ and list caches, tune mount flags or config-file settings, apply workload profiles,\ \ keep ML checkpointing safe (rename atomicity, hierarchical namespace, close-time\ \ finalization, concurrent writers), or diagnose slow training, low throughput,\ \ or GCS bill spikes on existing mounts with gcsfuse metrics. Covers mount semantics,\ \ the gcsfuse CLI and config file, the GKE gcsfuse CSI driver (Workload Identity\ \ principal:// bindings, profile StorageClasses, sidecar sizing), and Cloud Run\ \ volume mounts. Don't use for bucket administration or data management without\ \ a mount (google-cloud-storage-basics) or for fully POSIX-compliant shared file\ \ systems (Filestore, Managed Lustre).
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `google-cloud-storage-fuse` để phân tích và thực hiện tác vụ này.
  ```

### `managing-python-dependencies`
> **Mã định danh**: `managing-python-dependencies` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Ensures proper Python dependency management, avoiding global `pip install` and adhering to project-specific tooling. Use this skill if any of the following are true: 1. Attempting to run `pip install {package_name}`. 2. Python packages or dependencies need to be added or modified. 3. Initiating a new Python project. 4. Creating a new notebook, even if just using BigQuery cells. 5. Generating Python code that includes `import` statements for third-party libraries. 6. Before executing Python scripts via the terminal to ensure the correct virtual environment is active.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `managing-python-dependencies` để phân tích và thực hiện tác vụ này.
  ```

### `ml-best-practices`
> **Mã định danh**: `ml-best-practices` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  CRITICAL RULE: You MUST use this skill whenever the task involves any machine learning tasks or data analysis. Use this skill if the user's prompt or requirements mention any of the following: * Clustering * Classification * Regression * Time series forecasting * Statistical testing * Model comparison * ML * Data analysis SQL/BigQuery ML HANDOFF: If the user requires a SQL solution, use this skill to dictate the ANALYSIS STEPS (e.g., markdown analysis cells, visualization logic), but defer to `bigquery` for all SQL syntax.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `ml-best-practices` để phân tích và thực hiện tác vụ này.
  ```

### `notebook-guidance`
> **Mã định danh**: `notebook-guidance` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  - This skill guides the use of Jupyter notebooks for data analysis, exploration, and visualization, particularly with BigQuery. It outlines best practices for notebook execution and validation (supporting both cell-by-cell execution and full notebook generation depending on tool availability), library installation, and structuring notebooks for clarity. It also covers specific rules for data cleaning, plotting, and integrating with BigQuery SQL and machine learning workflows. Relevant when any of the following conditions are true: 1. The user request involves a data analysis, data exploration, data visualization, or data insights task that requires multiple steps, queries, or visualizations to answer. 2. The user explicitly requests a notebook (.ipynb). 3. You are creating, editing, or executing cells in a Jupyter notebook. 4. You need to query BigQuery from within a notebook. DO NOT use the Python BigQuery client library; instead, you MUST use the `%%bqsql` magics explained in this skill.
- **Điều kiện kích hoạt (When to use)**:
  📈 **Data Insights & Storytelling**: Use a notebook for any request to "give 📊 **Visualizations are requested**: The user explicitly asks for charts or 🔄 **Stateful / Iterative Exploration**: You need to run a query, inspect 📝 **Simple Fact/Status**: The request only requires a single number (e.g.,
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `notebook-guidance` để phân tích và thực hiện tác vụ này.
  ```

### `schema-mapping`
> **Mã định danh**: `schema-mapping` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Guides the process of analyzing, mapping, and documenting transformations between source and target schemas for any database, data warehouse, or data platform. Focuses exclusively on creating a high-fidelity mapping plan (Mapping Manifesto). Used when initiating an ETL, ELT, or data integration task with schema mapping specification for multiple tables (i.e. more than 3 tables) before writing code. Do NOT use this skill for basic SQL generation without mapping requirements, or when the user already has a complete mapping specification.
- **Điều kiện kích hoạt (When to use)**:
  You need to map schemas between a source dataset/database and a target You are initiating an ETL, ELT, or data integration task. You need to identify schema gaps, data type conflicts, or aggregation
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `schema-mapping` để phân tích và thực hiện tác vụ này.
  ```

### `skill-repair`
> **Mã định danh**: `skill-repair` | **Repository**: [GoogleCloudPlatform/datacloud-skills (Official Google Cloud)](https://github.com/GoogleCloudPlatform/datacloud-skills)

- **Tính năng chính**:
  Use this to fix and re-install agent skills that have failed installation. This skill provides the necessary context and permissions to surgically update the `manifest.json` after a fix has been applied.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `skill-repair` để phân tích và thực hiện tác vụ này.
  ```

---

## 4. Nhóm Agentic Engineering & Superpowers Suite

- **Repository nguồn**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)
- **Mô tả nhóm**: Bộ khung quy chuẩn phát triển phần mềm chuẩn mực (Software Engineering Methodology) dành cho AI Agent: Từ đặc tả, phân rã tác vụ, kiểm thử TDD, đơn giản hóa code, điều phối subagents đến rà soát bảo mật và phát hành.
- **Số lượng kỹ năng**: **30 skills**

### `api-and-interface-design`
> **Mã định danh**: `api-and-interface-design` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Guides stable API and interface design. Use when designing APIs, module boundaries, or any public interface. Use when creating REST or GraphQL endpoints, defining type contracts between modules, or establishing boundaries between frontend and backend.
- **Điều kiện kích hoạt (When to use)**:
  Design stable, well-documented interfaces that are hard to misuse. Good interfaces make the right thing easy and the wrong thing hard. This applies to REST APIs, GraphQL schemas, module boundaries, component props, and any surface where one piece of 
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `api-and-interface-design` để phân tích và thực hiện tác vụ này.
  ```

### `browser-testing-with-devtools`
> **Mã định danh**: `browser-testing-with-devtools` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Tests in real browsers via Chrome DevTools MCP. Use when building or debugging anything that runs in a browser. Use when you need to inspect the DOM, capture console errors, analyze network requests, profile performance, or verify visual output with real runtime data. Requires the chrome-devtools MCP server to be configured.
- **Điều kiện kích hoạt (When to use)**:
  Use Chrome DevTools MCP to give your agent eyes into the browser. This bridges the gap between static code analysis and live browser execution — the agent can see what the user sees, inspect the DOM, read console logs, analyze network requests, and c
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `browser-testing-with-devtools` để phân tích và thực hiện tác vụ này.
  ```

### `ci-cd-and-automation`
> **Mã định danh**: `ci-cd-and-automation` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Automates CI/CD pipeline setup. Use when setting up or modifying build and deployment pipelines. Use when you need to automate quality gates, configure test runners in CI, or establish deployment strategies.
- **Điều kiện kích hoạt (When to use)**:
  Automate quality gates so that no change reaches production without passing tests, lint, type checking, and build. CI/CD is the enforcement mechanism for every other skill — it catches what humans and agents miss, and it does so consistently on every
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `ci-cd-and-automation` để phân tích và thực hiện tác vụ này.
  ```

### `code-review-and-quality`
> **Mã định danh**: `code-review-and-quality` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Conducts multi-axis code review. Use before merging any change. Use when reviewing code written by yourself, another agent, or a human. Use when you need to assess code quality across multiple dimensions before it enters the main branch.
- **Điều kiện kích hoạt (When to use)**:
  Multi-dimensional code review with quality gates. Every change gets reviewed before merge — no exceptions. Review covers five axes: correctness, readability, architecture, security, and performance.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `code-review-and-quality` để phân tích và thực hiện tác vụ này.
  ```

### `code-simplification`
> **Mã định danh**: `code-simplification` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Simplifies code for clarity. Use when refactoring code for clarity without changing behavior. Use when code works but is harder to read, maintain, or extend than it should be. Use when reviewing code that has accumulated unnecessary complexity.
- **Điều kiện kích hoạt (When to use)**:
  Simplify code by reducing complexity while preserving exact behavior. The goal is not fewer lines — it's code that is easier to read, understand, modify, and debug. Every simplification must pass a simple test: "Would a new team member understand thi
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `code-simplification` để phân tích và thực hiện tác vụ này.
  ```

### `context-engineering`
> **Mã định danh**: `context-engineering` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Optimizes agent context setup. Use when starting a new session, when agent output quality degrades, when switching between tasks, or when you need to configure rules files and context for a project.
- **Điều kiện kích hoạt (When to use)**:
  Feed agents the right information at the right time. Context is the single biggest lever for agent output quality — too little and the agent hallucinates, too much and it loses focus. Context engineering is the practice of deliberately curating what 
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `context-engineering` để phân tích và thực hiện tác vụ này.
  ```

### `debugging-and-error-recovery`
> **Mã định danh**: `debugging-and-error-recovery` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Guides systematic root-cause debugging. Use when tests fail, builds break, behavior doesn't match expectations, or you encounter any unexpected error. Use when you need a systematic approach to finding and fixing the root cause rather than guessing.
- **Điều kiện kích hoạt (When to use)**:
  Systematic debugging with structured triage. When something breaks, stop adding features, preserve evidence, and follow a structured process to find and fix the root cause. Guessing wastes time. The triage checklist works for test failures, build err
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `debugging-and-error-recovery` để phân tích và thực hiện tác vụ này.
  ```

### `deprecation-and-migration`
> **Mã định danh**: `deprecation-and-migration` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Manages deprecation and migration. Use when removing old systems, APIs, or features. Use when migrating users from one implementation to another. Use when deciding whether to maintain or sunset existing code.
- **Điều kiện kích hoạt (When to use)**:
  Code is a liability, not an asset. Every line of code has ongoing maintenance cost — bugs to fix, dependencies to update, security patches to apply, and new engineers to onboard. Deprecation is the discipline of removing code that no longer earns its
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `deprecation-and-migration` để phân tích và thực hiện tác vụ này.
  ```

### `dispatching-parallel-agents`
> **Mã định danh**: `dispatching-parallel-agents` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Coordinates multiple subagents working on different tasks simultaneously. Use when you have identified 2+ truly independent tasks that can run in parallel to reduce total execution time. Use when the task decomposition from planning-and-task-breakdown or subagent-driven-development yields parallelizable work units.
- **Điều kiện kích hoạt (When to use)**:
  When a plan reveals multiple independent work units, dispatch them in parallel
to dramatically reduce total execution time. But parallelism adds coordination
complexity — this skill provides the guardrails to prevent conflicts, ensure
consistency, an
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `dispatching-parallel-agents` để phân tích và thực hiện tác vụ này.
  ```

### `documentation-and-adrs`
> **Mã định danh**: `documentation-and-adrs` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Records decisions and documentation. Use when making architectural decisions, changing public APIs, shipping features, or when you need to record context that future engineers and agents will need to understand the codebase.
- **Điều kiện kích hoạt (When to use)**:
  Document decisions, not just code. The most valuable documentation captures the *why* — the context, constraints, and trade-offs that led to a decision. Code shows *what* was built; documentation explains *why it was built this way* and *what alterna
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `documentation-and-adrs` để phân tích và thực hiện tác vụ này.
  ```

### `doubt-driven-development`
> **Mã định danh**: `doubt-driven-development` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Subjects every non-trivial decision to a fresh-context adversarial review before it stands. Use when correctness matters more than speed, when working in unfamiliar code, when stakes are high (production, security-sensitive logic, irreversible operations), or any time a confident output would be cheaper to verify now than to debug later.
- **Điều kiện kích hoạt (When to use)**:
  A confident answer is not a correct one. Long sessions accumulate context that quietly turns assumptions into "facts" without anyone noticing. Doubt-driven development is the discipline of materializing a fresh-context reviewer — biased to **disprove
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `doubt-driven-development` để phân tích và thực hiện tác vụ này.
  ```

### `frontend-design`
> **Mã định danh**: `frontend-design` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Guidance for distinctive, intentional visual design when building new UI or reshaping an existing one. Helps with aesthetic direction, typography, and making choices that don't read as templated defaults.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `frontend-design` để phân tích và thực hiện tác vụ này.
  ```

### `frontend-ui-engineering`
> **Mã định danh**: `frontend-ui-engineering` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Builds production-quality UIs. Use when building or modifying user-facing interfaces. Use when creating components, implementing layouts, managing state, or when the output needs to look and feel production-quality rather than AI-generated.
- **Điều kiện kích hoạt (When to use)**:
  Build production-quality user interfaces that are accessible, performant, and visually polished. The goal is UI that looks like it was built by a design-aware engineer at a top company — not like it was generated by an AI. This means real design syst
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `frontend-ui-engineering` để phân tích và thực hiện tác vụ này.
  ```

### `git-workflow-and-versioning`
> **Mã định danh**: `git-workflow-and-versioning` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Structures git workflow practices. Use when making any code change. Use when committing, branching, resolving conflicts, or when you need to organize work across multiple parallel streams. Use when cutting a release, choosing a semantic version bump, tagging, or writing a changelog.
- **Điều kiện kích hoạt (When to use)**:
  Git is your safety net. Treat commits as save points, branches as sandboxes, and history as documentation. With AI agents generating code at high speed, disciplined version control is the mechanism that keeps changes manageable, reviewable, and rever
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `git-workflow-and-versioning` để phân tích và thực hiện tác vụ này.
  ```

### `idea-refine`
> **Mã định danh**: `idea-refine` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Refines raw ideas into sharp, actionable concepts through structured divergent and convergent thinking. Use when an idea is still vague, when you need to stress-test assumptions before committing to a plan, or when you want to expand options before converging on one. Triggers on "ideate", "refine this idea", or "stress-test my plan".
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `idea-refine` để phân tích và thực hiện tác vụ này.
  ```

### `incremental-implementation`
> **Mã định danh**: `incremental-implementation` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Delivers changes incrementally. Use when implementing any feature or change that touches more than one file. Use when you're about to write a large amount of code at once, or when a task feels too big to land in one step.
- **Điều kiện kích hoạt (When to use)**:
  Build in thin vertical slices — implement one piece, test it, verify it, then expand. Avoid implementing an entire feature in one pass. Each increment should leave the system in a working, testable state. This is the execution discipline that makes l
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `incremental-implementation` để phân tích và thực hiện tác vụ này.
  ```

### `interview-me`
> **Mã định danh**: `interview-me` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Extracts what the user actually wants instead of what they think they should want. Achieves this through one-question-at-a-time interview until ~95% confidence about the underlying intent. Use when an ask is underspecified ("build me X" without "for whom" or "why now"), when the user explicitly invokes ("interview me", "grill me", "are we sure?", "stress-test my thinking"), or when you catch yourself silently filling in ambiguous requirements before any plan, spec, or code exists.
- **Điều kiện kích hoạt (When to use)**:
  What people ask for and what they actually want are different things. They ask for "a dashboard" because that's what one asks for, not because a dashboard solves their problem. They say "make it faster" without a number to hit.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `interview-me` để phân tích và thực hiện tác vụ này.
  ```

### `observability-and-instrumentation`
> **Mã định danh**: `observability-and-instrumentation` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Instruments code so production behavior is visible and diagnosable. Use when adding logging, metrics, tracing, or alerting. Use when shipping any feature that runs in production and you need evidence it works. Use when production issues are reported but you can't tell what happened from the available data.
- **Điều kiện kích hoạt (When to use)**:
  Code you can't observe is code you can't operate. Observability is the ability to answer "what is the system doing and why?" from the outside, using the telemetry the code emits. Instrumentation is not a post-launch add-on — it's written alongside th
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `observability-and-instrumentation` để phân tích và thực hiện tác vụ này.
  ```

### `performance-optimization`
> **Mã định danh**: `performance-optimization` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Optimizes application performance. Use when performance requirements exist, when you suspect performance regressions, or when Core Web Vitals or load times need improvement. Use when profiling reveals bottlenecks that need fixing.
- **Điều kiện kích hoạt (When to use)**:
  Measure before optimizing. Performance work without measurement is guessing — and guessing leads to premature optimization that adds complexity without improving what matters. Profile first, identify the actual bottleneck, fix it, measure again. Opti
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `performance-optimization` để phân tích và thực hiện tác vụ này.
  ```

### `planning-and-task-breakdown`
> **Mã định danh**: `planning-and-task-breakdown` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Breaks work into ordered tasks. Use when you have a spec or clear requirements and need to break work into implementable tasks. Use when a task feels too large to start, when you need to estimate scope, or when parallel work is possible.
- **Điều kiện kích hoạt (When to use)**:
  Decompose work into small, verifiable tasks with explicit acceptance criteria. Good task breakdown is the difference between an agent that completes work reliably and one that produces a tangled mess. Every task should be small enough to implement, t
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `planning-and-task-breakdown` để phân tích và thực hiện tác vụ này.
  ```

### `security-and-hardening`
> **Mã định danh**: `security-and-hardening` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Hardens code against vulnerabilities. Use when handling user input, authentication, data storage, or external integrations. Use when building any feature that accepts untrusted data, manages user sessions, or interacts with third-party services.
- **Điều kiện kích hoạt (When to use)**:
  Security-first development practices for web applications. Treat every external input as hostile, every secret as sacred, and every authorization check as mandatory. Security isn't a phase — it's a constraint on every line of code that touches user d
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `security-and-hardening` để phân tích và thực hiện tác vụ này.
  ```

### `shipping-and-launch`
> **Mã định danh**: `shipping-and-launch` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Prepares production launches. Use when preparing to deploy to production. Use when you need a pre-launch checklist, when setting up monitoring, when planning a staged rollout, or when you need a rollback strategy.
- **Điều kiện kích hoạt (When to use)**:
  Ship with confidence. The goal is not just to deploy — it's to deploy safely, with monitoring in place, a rollback plan ready, and a clear understanding of what success looks like. Every launch should be reversible, observable, and incremental.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `shipping-and-launch` để phân tích và thực hiện tác vụ này.
  ```

### `source-driven-development`
> **Mã định danh**: `source-driven-development` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Grounds every implementation decision in official documentation. Use when you want authoritative, source-cited code free from outdated patterns. Use when building with any framework or library where correctness matters.
- **Điều kiện kích hoạt (When to use)**:
  Every framework-specific code decision must be backed by official documentation. Don't implement from memory — verify, cite, and let the user see your sources. Training data goes stale, APIs get deprecated, best practices evolve. This skill ensures t
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `source-driven-development` để phân tích và thực hiện tác vụ này.
  ```

### `spec-driven-development`
> **Mã định danh**: `spec-driven-development` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Creates specs before coding. Use when starting a new project, feature, or significant change and no specification exists yet. Use when requirements are unclear, ambiguous, or only exist as a vague idea.
- **Điều kiện kích hoạt (When to use)**:
  Write a structured specification before writing any code. The spec is the shared source of truth between you and the human engineer — it defines what we're building, why, and how we'll know it's done. Code without a spec is guessing.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `spec-driven-development` để phân tích và thực hiện tác vụ này.
  ```

### `subagent-driven-development`
> **Mã định danh**: `subagent-driven-development` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Structures how to dispatch, review, and integrate subagent work for complex multi-component tasks. Use when a task involves 3+ files, multiple independent components, or when the scope would benefit from parallel specialized work. Use when you're about to launch subagents and need a protocol for quality control.
- **Điều kiện kích hoạt (When to use)**:
  When a task is complex enough to benefit from delegation, dispatch specialized
subagents to handle independent components — but never without structure. Each
subagent receives a clear brief, works within defined boundaries, and its output
goes throug
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `subagent-driven-development` để phân tích và thực hiện tác vụ này.
  ```

### `superpowers-orchestration`
> **Mã định danh**: `superpowers-orchestration` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Automatically chains the right skills together based on task complexity. This is the orchestration layer inspired by obra/superpowers methodology. Always active — classifies every incoming request and triggers the appropriate workflow: direct execution for simple tasks, structured planning for complex ones, and subagent-driven development for large multi-component work.
- **Điều kiện kích hoạt (When to use)**:
  This is the **orchestration methodology** that automatically classifies incoming
requests and chains the appropriate skills together. Instead of applying skills
ad-hoc, this rule ensures a disciplined, predictable workflow fires every time.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `superpowers-orchestration` để phân tích và thực hiện tác vụ này.
  ```

### `test-driven-development`
> **Mã định danh**: `test-driven-development` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Drives development with tests. Use when implementing any logic, fixing any bug, or changing any behavior. Use when you need to prove that code works, when a bug report arrives, or when you're about to modify existing functionality.
- **Điều kiện kích hoạt (When to use)**:
  Write a failing test before writing the code that makes it pass. For bug fixes, reproduce the bug with a test before attempting a fix. Tests are proof — "seems right" is not done. A codebase with good tests is an AI agent's superpower; a codebase wit
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `test-driven-development` để phân tích và thực hiện tác vụ này.
  ```

### `ui-ux-pro-max`
> **Mã định danh**: `ui-ux-pro-max` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  UI/UX design intelligence for web and mobile. Searchable local database with 50+ styles, 161 color palettes, 57 font pairings, 161 product types, 99 UX guidelines, and 25 chart types across 10 stacks (React, Next.js, Vue, Svelte, SwiftUI, React Native, Flutter, Tailwind, shadcn/ui, and HTML/CSS). Use when designing, building, or reviewing UI: pages, components, color schemes, typography, layout, accessibility, animation, or data visualization.
- **Điều kiện kích hoạt (When to use)**:
  Designing new pages (Landing Page, Dashboard, Admin, SaaS, Mobile App) Creating or refactoring UI components (buttons, modals, forms, tables, charts, etc.) Choosing color schemes, typography systems, spacing standards, or layout systems Reviewing UI code for user experience, accessibility, or visual consistency
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `ui-ux-pro-max` để phân tích và thực hiện tác vụ này.
  ```

### `using-agent-skills`
> **Mã định danh**: `using-agent-skills` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Discovers and invokes agent skills. Use when starting a session or when you need to discover which skill applies to the current task. This is the meta-skill that governs how all other skills are discovered and invoked.
- **Điều kiện kích hoạt (When to use)**:
  Agent Skills is a collection of engineering workflow skills organized by development phase. Each skill encodes a specific process that senior engineers follow. This meta-skill helps you discover and apply the right skill for your current task.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `using-agent-skills` để phân tích và thực hiện tác vụ này.
  ```

### `verification-before-completion`
> **Mã định danh**: `verification-before-completion` | **Repository**: [obra/superpowers & Senior Engineering Workflows](https://github.com/obra/superpowers)

- **Tính năng chính**:
  Ensures proof of correctness exists before any task is marked as done. Use before reporting completion of any coding task. Use when you're about to say "done" or "completed" to verify that evidence supports the claim. This is the final gate before every task closes.
- **Điều kiện kích hoạt (When to use)**:
  Never claim a task is "done" without evidence. Before reporting completion,
systematically verify that the work actually works — with proof. This prevents
the common agent failure mode of confidently declaring completion while bugs,
missing edge case
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `verification-before-completion` để phân tích và thực hiện tác vụ này.
  ```

---

## 5. Nhóm Google Antigravity Built-in Core Skills

- **Repository nguồn**: [Google Antigravity Built-in](https://github.com/google/antigravity)
- **Mô tả nhóm**: Bộ kỹ năng lõi tích hợp sẵn trong nền tảng Antigravity để điều hướng giao diện, tự động hóa tác vụ ngầm, sinh widget trực quan và quản trị extension/plugin.
- **Số lượng kỹ năng**: **9 skills**

### `agy-customizations`
> **Mã định danh**: `agy-customizations` | **Repository**: [Google Antigravity Built-in](https://github.com/google/antigravity)

- **Tính năng chính**:
  Comprehensive guide and reference for the Antigravity Customization System. Use to explain how customizations work, their loading priority, discovery mechanisms, and to guide the creation of skills, rules, plugins, hooks, and MCP servers.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `agy-customizations` để phân tích và thực hiện tác vụ này.
  ```

### `antigravity-guide`
> **Mã định danh**: `antigravity-guide` | **Repository**: [Google Antigravity Built-in](https://github.com/google/antigravity)

- **Tính năng chính**:
  Kỹ năng chuyên biệt.
- **Điều kiện kích hoạt (When to use)**:
  K h i   đ ư ợ c   g ọ i   t r ự c   t i ế p   h o ặ c   k h i   t á c   v ụ   y ê u   c ầ u .
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `antigravity-guide` để phân tích và thực hiện tác vụ này.
  ```

### `automation`
> **Mã định danh**: `automation` | **Repository**: [Google Antigravity Built-in](https://github.com/google/antigravity)

- **Tính năng chính**:
  Interactive guide to design and create a scheduled background automation. Use this skill when the user wants to create an automated or recurring scheduled task (e.g. "summarize my emails every morning", "every Monday send me a to-do list"). Also triggered by the /automation slash command.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `automation` để phân tích và thực hiện tác vụ này.
  ```

### `generative_ui`
> **Mã định danh**: `generative_ui` | **Repository**: [Google Antigravity Built-in](https://github.com/google/antigravity)

- **Tính năng chính**:
  How to render rich interactive HTML widgets inline in the chat or as standalone artifacts. Use this skill when you want to show the user diagrams, data visualizations, interactive controls, educational walkthroughs, or any rich visual content beyond plain text and markdown.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `generative_ui` để phân tích và thực hiện tác vụ này.
  ```

### `migrate-workflows`
> **Mã định danh**: `migrate-workflows` | **Repository**: [Google Antigravity Built-in](https://github.com/google/antigravity)

- **Tính năng chính**:
  Automatically migrate legacy workflows to modern skills across global and workspace configurations. Scans for existing workflows, creates target SKILL.md files, and safely archives old workflow files.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `migrate-workflows` để phân tích và thực hiện tác vụ này.
  ```

### `permissioned-github`
> **Mã định danh**: `permissioned-github` | **Repository**: [Google Antigravity Built-in](https://github.com/google/antigravity)

- **Tính năng chính**:
  Guidelines for interacting with GitHub and request permissions from the user when commands fail due to restrictions in the agent environment.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `permissioned-github` để phân tích và thực hiện tác vụ này.
  ```

### `plugin`
> **Mã định danh**: `plugin` | **Repository**: [Google Antigravity Built-in](https://github.com/google/antigravity)

- **Tính năng chính**:
  How to manage and create plugins — namespaced bundles of skills, agents, rules, MCP servers and hooks that install, enable and disable as a single unit. Use this skill when the user wants to enable, disable, install or uninstall a plugin, when they want to create a new plugin, or when a new customization should be packaged into a plugin rather than left loose. Also triggered by the /plugin slash command. Don't use for the underlying customization system itself — discovery roots, loading priority, or authoring a standalone skill, agent, rule, hook or MCP server outside a plugin; see the customizations guide skill for those.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `plugin` để phân tích và thực hiện tác vụ này.
  ```

### `run-workflow`
> **Mã định danh**: `run-workflow` | **Repository**: [Google Antigravity Built-in](https://github.com/google/antigravity)

- **Tính năng chính**:
  How to write and run a dynamic workflow script with the `run_workflow` tool: a Python script that orchestrates many agents with `agent`, `parallel`, `pipeline`, and `phase`. Use when a task splits into many independent or staged pieces of agent work (fan out over files, modules, bugs, or review angles, then aggregate), or when the user asks for a workflow. Don't use for a single delegated task (use a subagent) or for legacy workflow files (see migrate-workflows).
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `run-workflow` để phân tích và thực hiện tác vụ này.
  ```

### `ui-plugin-navigation`
> **Mã định danh**: `ui-plugin-navigation` | **Repository**: [Google Antigravity Built-in](https://github.com/google/antigravity)

- **Tính năng chính**:
  Discover UI plugin panels relevant to the current task and surface a one-click pill in chat to open (toggle) them in the side pane. Use when a running UI plugin's panel would help with what the user is doing, or right after the user enables a new UI plugin pane and a shortcut to open it is handy.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `ui-plugin-navigation` để phân tích và thực hiện tác vụ này.
  ```

---

## 6. Nhóm AI Slide Presentation & Deck Generators

- **Repository nguồn**: [Community PPT Skills (op7418/guizang-ppt-skill & hugohe3/ppt-master)](https://github.com/op7418/guizang-ppt-skill)
- **Mô tả nhóm**: Các kỹ năng chuyên sâu để kiến tạo bài thuyết trình chuyên nghiệp, thiết kế slide web tương tác cao, tạo mẫu PPTX và chuyển đổi dàn ý sang slide hoàn chỉnh.
- **Số lượng kỹ năng**: **2 skills**

### `guizang-ppt-skill`
> **Mã định danh**: `guizang-ppt-skill` | **Repository**: [Community PPT Skills (op7418/guizang-ppt-skill & hugohe3/ppt-master)](https://github.com/op7418/guizang-ppt-skill)

- **Tính năng chính**:
  生成横向翻页网页 PPT（单 HTML 文件），含 WebGL 背景、演讲者视图、观众屏同步、讲稿备注、章节幕封、数据大字报、图片网格等模板。提供两种风格：① "电子杂志 × 电子墨水"（衬线 + 流体背景 + 暖色） ② "瑞士国际主义"（无衬线 + 网格点阵 + IKB/柠檬黄/柠檬绿/安全橙高亮）。当用户需要制作分享 / 演讲 / 发布会风格的网页 PPT，或提到"杂志风 PPT"、"瑞士风 PPT"、"Swiss Style"、"horizontal swipe deck"时使用。
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `guizang-ppt-skill` để phân tích và thực hiện tác vụ này.
  ```

### `ppt-master`
> **Mã định danh**: `ppt-master` | **Repository**: [Community PPT Skills (op7418/guizang-ppt-skill & hugohe3/ppt-master)](https://github.com/op7418/guizang-ppt-skill)

- **Tính năng chính**:
  AI-driven presentation workflow for generating editable PPTX decks and slides, reconstructing page visuals, creating reusable Brand/Style/Layout/Deck workspaces, filling native PPTX templates, and enhancing finished PPTX files. Use when the user asks to create, generate, reconstruct, regenerate, beautify, redesign, template, fill, or enhance a presentation, PPT, PPTX, slide deck, or courseware — including adding narration or animation to one — requests a presentation-authored narrated/self-running video, or mentions ppt-master.
- **Điều kiện kích hoạt (When to use)**:
  Kích hoạt khi gặp tác vụ tương ứng với phạm vi kỹ thuật của skill hoặc khi người dùng yêu cầu trực tiếp.
- **Cách sử dụng & Prompt mẫu**:
  ```text
  Hãy áp dụng kỹ năng `ppt-master` để phân tích và thực hiện tác vụ này.
  ```

---

## Ma trận Kích hoạt Skill theo Giai đoạn Phát triển (Skill Trigger Matrix)

Để tối ưu hóa luồng làm việc, AI Agent tự động chọn chuỗi kỹ năng theo sơ đồ phân loại 3 cấp độ (Tier Classification) từ `superpowers-orchestration`:

```text
Yêu cầu người dùng gửi đến
  │
  ├── Cấp độ 1: Tác vụ nhanh (<30 dòng, 1 file, rõ ràng)
  │     └── Thực thi trực diện ──→ verification-before-completion ──→ Hoàn thành
  │
  ├── Cấp độ 2: Tác vụ chuẩn (1-3 file, yêu cầu rõ nhưng cần suy nghĩ)
  │     ├── Làm rõ yêu cầu (nếu mơ hồ) ──→ interview-me
  │     ├── Lên kế hoạch ────────────────→ planning-and-task-breakdown
  │     ├── Phát triển theo kiểm thử ────→ test-driven-development
  │     ├── Triển khai từng bước ────────→ incremental-implementation
  │     ├── Tinh gọn code ───────────────→ code-simplification
  │     └── Xác thực kết quả ────────────→ verification-before-completion
  │
  └── Cấp độ 3: Tác vụ phức tạp (Đa thành phần, kiến trúc mới, đổi DB)
        ├── Khảo sát & phỏng vấn ────────→ interview-me & idea-refine
        ├── Viết đặc tả kiến trúc ───────→ spec-driven-development & documentation-and-adrs
        ├── Phản biện độc lập ───────────→ doubt-driven-development
        ├── Thiết kế giao diện / API ────→ frontend-ui-engineering & api-and-interface-design
        ├── Phân rã subagent chạy song song → dispatching-parallel-agents & subagent-driven-development
        ├── Kiểm thử & rà soát bảo mật ──→ code-review-and-quality & security-and-hardening
        └── Đóng gói phát hành ──────────→ shipping-and-launch & git-workflow-and-versioning
```

---
*Tài liệu được biên soạn tự động và đồng bộ với hệ thống kho lưu trữ mã nguồn GitHub.*