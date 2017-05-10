#### 1. Tool nào cần dùng để test ble?
#### 2. Kiến thức cơ bản về ble?
#### 3. iBeacon & beacon & Eddystone là gì?
#### 4. Tốc độ của ble là bao nhiêu trên android & iOS?
#### 5. Số lượng thiết bị tối đa kết nối cùng một lúc là cbao nhiêu?
#### 6. APNS của apple là gì?
#### 7. Pair & unpair device trên android & iOS ra sao?
#### 8. Cơ chế hoạt động của ble trên iOS như thế nào ở mode backgroudnd & forground & app fore stop?
#### 9. Tìm hiểu thư viện wrapper trên android & iOS và chạy example mẫu
#### 10. Tăng tốc write 
#### 11. Max packet length

### Trả lời

#### 1. Tool nào cần dùng để test ble?
	- iOS: LightBlue
	- Android: nRF Connect

#### 2. Kiến thức cơ bản về ble?
	- Đọc cuốn Getting Started with Bluetooth Low Energy-1.pdf.
	Đọc chương 1 & 2 & 3, riêng chương 3 đọc kỹ

	- Cần nắm các thuật ngữ sau:
		+ Scan
		+ Kết nối
		+ Peripheral & Manager
		+ Service, characteristic
		+ read, write, notify
		+ mtu, 
		+ Quảng bá (Advertising)
		+ Address
		+ Connection interval & giá trị trên android và iOS là bao nhiêu
		+ Supervison timout

#### 3. iBeacon & beacon & Eddystone là gì & khác với ble thường ở điểm nào?
	- iBeacon: https://en.wikipedia.org/wiki/IBeacon
	- Beacon: https://en.wikipedia.org/wiki/Bluetooth_low_energy_beacon
	- Eddystone: https://developers.google.com/beacons/

#### 10. Tăng tốc write 
	- Chọn write type without response
	- 

#### 11. Max packet length
	20 bytes data không bao gồm các header + CRC + ... của các layer bên dưới
