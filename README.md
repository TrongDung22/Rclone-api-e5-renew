# Rclone-api-e5-renew
Thay vì call các API của bọn khựa thì ae có thể dùng rclone, vừa down/up/sync file, vừa auto renew E5

Mình dùng E5 nhiều năm rồi. Chỉ cài mỗi onedrive trên phone để sync ảnh, lâu lâu dùng rclone copy vài file vào Drive (Ko có tạo share point, ko active office, ko github...) Và vẫn đc renew bình thường.

Các bạn có thể thử xem nhé~~~

Cách làm như sau:

Truy cập https://portal.azure.com/#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade
 Click New registration tạo 1 app (Nhớ copy lại Application (client) ID)
3. Click Certificates & secrets --> New customer secret (Chọn Expires là 24 months). Sau khi tạo xong copy lại secret value

 

4. Authorized APIs --> Add permissions --> Microsoft Graph --> Delegrated permission

 Chọn những quyền sau: Files.Read, Files.ReadWrite, Files.Read.All, Files.ReadWrite.All, offline_access, User.Read and Sites.Read.All --> Add

 

5. Cài đặt rclone xong thì add OneDrive

rclone config

Đặt tên tùy chọnP
Paste Application Id ở bước 2P
Paste Secret ID ở bước 3
Chọn 1 (Microsoft Cloud Global)
Chọn n
Các bước sau, authen làm như bình thường
