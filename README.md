# Hướng Dẫn Deep Learning Bằng Synthetic Data Cho Mô Hình LLaMA 3.2

## Giới Thiệu
Bài viết này cung cấp hướng dẫn chi tiết về cách sử dụng synthetic data để huấn luyện mô hình LLaMA 3.2. Quy trình bao gồm việc tạo dữ liệu từ tài liệu giáo trình, định dạng dữ liệu phù hợp và thực hiện huấn luyện mô hình.

## Phần 1: Chuẩn Bị Dữ Liệu Synthetic

### 1. Tạo Dữ Liệu Synthetic
- Sử dụng `synthetic-data-kit` để tạo ra dữ liệu QA từ nguồn tài liệu có sẵn (giáo trình, sách, v.v.).
- Định nghĩa các thông số đầu vào cho quá trình tạo dữ liệu.

### 2. Định Dạng Dữ Liệu
- Chuyển đổi dữ liệu từ định dạng gốc sang định dạng phù hợp với LLaMA 3.2.
  
**Định dạng gốc:**
```json
{
  "from": "human",
  "value": "{câu hỏi}"
},
{
  "from": "gpt",
  "value": "{Câu trả lời}"
}
```
Định dạng LLaMA:
```json
{
  "messages": [
    {"role": "system", "content": "..."},
    {"role": "user", "content": "{Câu hỏi}"},
    {"role": "assistant", "content": "{Câu trả lời}"}
  ]
}
```
## Huấn Luyện Mô Hình LLaMA 3.2
### Sử dụng google colab [📓Notebook train AI](https://colab.research.google.com/github/unslothai/notebooks/blob/main/nb/Meta_Synthetic_Data_Llama3_2_(3B).ipynb)

1. Thiết Lập Môi Trường Huấn Luyện
Sử dụng thư viện SFTTrainer để thực hiện quá trình huấn luyện.
2. Tối Ưu Tốc Độ và Bộ Nhớ
Sử dụng thư viện Unsloth để tối ưu hóa tốc độ và bộ nhớ của GPU.
3. Thực Hiện Huấn Luyện
Huấn luyện mô hình với 500 bước (steps) dựa trên bộ dữ liệu đã được định dạng.
Phần 3: Lưu Dữ Liệu và Kết Thúc
1. Lưu Mô Hình
Lưu mô hình dưới dạng .gguf
2. Kiểm Tra Mô Hình
Sử dụng UI để có thể chạy được model có thể là web-ui hoặc app 
# 👋[jan.ai](https://github.com/menloresearch/jan)


[Demo](demo) 8gb VRAM



