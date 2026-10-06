Khái niệm

Table = một sheet; row = một bản ghi; column = một thuộc tính.
Tách bảng để tránh lặp dữ liệu: thông tin chỉ lưu một lần, sửa một chỗ là đủ.
Primary key (PK): phân biệt từng dòng. Không trùng, không NULL, mỗi bảng đúng một PK.
Foreign key (FK): cột trỏ sang PK của bảng khác. FK được trùng, nhưng giá trị đó phải tồn tại ở bảng đích.
Composite PK: PK ghép từ nhiều cột, ví dụ film_actor (actor_id, film_id).
Junction table: bảng trung gian cho quan hệ nhiều–nhiều, như film_actor hay bảng điểm (student_id, unit_code).
Quan hệ logic khác ràng buộc FK: cột có thể mang ý nghĩa FK mà không được khai báo (như store_id trong customer). Khi không có constraint, database không chặn dữ liệu sai (referential integrity).

Cách kiểm tra

Một cột làm PK được không? Hỏi: "Cột này có bao giờ trùng không?"
Một cột là FK không? Hỏi: "Có bảng đích để nó trỏ tới không?"
Trong DBeaver: Properties → Columns / Constraints / Foreign Keys.

Ví dụ dvdrental

Bảng	PK	FK
rental	rental_id	customer_id, inventory_id, staff_id
film_actor	(actor_id, film_id)	actor_id, film_id
address	address_id	city_id
film = bộ phim (một bản); inventory = từng đĩa thật. rental trỏ vào inventory.

Lỗi đã mắc

Nhầm tên ràng buộc (fk_address_city) với tên cột (city_id).
Nghĩ film_actor không có PK (thực ra là composite PK).
Nghĩ postal_code là FK (không có bảng đích).
Lý do tách bảng: không phải vì trùng tên, mà vì tránh lặp dữ liệu.# Learning notes
