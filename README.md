def remove_duplicates_from_file(input_file, output_file):
    try:
        # Mở file đọc dữ liệu
        with open(input_file, 'r', encoding='utf-8') as file:
            lines = file.readlines()
        
        # Loại bỏ các dòng trùng lặp bằng cách dùng set
        unique_lines = set(line.strip() for line in lines)
        
        # Ghi kết quả vào file mới
        with open(output_file, 'w', encoding='utf-8') as file:
            for line in sorted(unique_lines):  # Sắp xếp nếu cần
                file.write(line + '\n')
        
        print(f"Đã loại bỏ các phần trùng lặp. Kết quả được lưu tại: {output_file}")
    except Exception as e:
        print(f"Có lỗi xảy ra: {e}")

# Sử dụng hàm
remove_duplicates_from_file('input.txt', 'output.txt')

