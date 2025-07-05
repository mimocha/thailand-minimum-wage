# Thailand Minimum Wage Dataset

*(คำอธิบายภาษาไทยอยู่ด้านล่าง)*

Thailand minimum daily wage dataset, as sourced from the official
[Thailand Ministry of Labour website.](https://www.mol.go.th/%E0%B8%AD%E0%B8%B1%E0%B8%95%E0%B8%A3%E0%B8%B2%E0%B8%84%E0%B9%88%E0%B8%B2%E0%B8%88%E0%B9%89%E0%B8%B2%E0%B8%87%E0%B8%82%E0%B8%B1%E0%B9%89%E0%B8%99%E0%B8%95%E0%B9%88%E0%B8%B3)

I've transcribed the data (Excel / PDF) into a more machine-usable format out of curiosity.

![Data Example](assets/example_data.png)

This data should allow for easier analysis for whatever you are interested in.

![Chart Example](assets/example_chart.png)

### Usage

- The dataset is in the file `minimum-wage-by-province.csv`
- Columns 1 & 2 are the source of announcement & announcement number (based on the MoL Excel file below)
- Column 3 `announce` is the announcement date in ISO format string, with the Thai Buddhist era calendar
- Column 4 `effective` is when the new minimum wage takes effect in ISO format string, with the Thai Buddhist era calendar
- The remaining columns are Thai province names in Thai (e.g. `กรุงเทพมหานคร,กระบี่,กาญจนบุรี...`) sorted in alphabetical order
- Each cell entry contains the new effective minimum wage for each province (column), in that announcement (row)
- If an announcement does not change the minimum wage for a province, the entry will be left empty

### Important Note
This dataset only captures the minimum wage of each province.
More complex cases like these are not properly captured:
- Minimum wage change by Amphoe / District
    - In cases where certain Amphoe have a higher minimum wage than the rest of the province, I use the _lower minimum wage value_ to represent that province
- Minimum wage change by industry / profession
    - I ignore changes by specific industries / professions entirely

Specifically, this includes the latest two changes, which targets specific Amphoe and professions:
- [Jan 1st 2025 changes](https://www.mol.go.th/wp-content/uploads/sites/2/2024/12/%E0%B8%9B%E0%B8%A3%E0%B8%B0%E0%B8%81%E0%B8%B2%E0%B8%A8%E0%B8%84%E0%B9%88%E0%B8%B2%E0%B8%88%E0%B9%89%E0%B8%B2%E0%B8%87%E0%B8%82%E0%B8%B1%E0%B9%89%E0%B8%99%E0%B8%95%E0%B9%88%E0%B8%B3-%E0%B8%8913%E0%B8%A3%E0%B8%B2%E0%B8%8A%E0%B8%81%E0%B8%B4%E0%B8%88%E0%B8%88%E0%B8%B2.pdf)
- [July 1st 2025 changes](https://www.mol.go.th/wp-content/uploads/sites/2/2025/07/%E0%B8%9B%E0%B8%A3%E0%B8%B0%E0%B8%81%E0%B8%B2%E0%B8%A8-%E0%B8%84%E0%B8%88.%E0%B8%82%E0%B8%B1%E0%B9%89%E0%B8%99%E0%B8%95%E0%B9%88%E0%B8%B3-%E0%B8%8914-%E0%B8%A3%E0%B8%A7%E0%B8%A1.pdf)

Older announcements (specifically those made by กระทรวงมหาดไทย) are sometimes ambiguous.
I am unable to find the original documents to clarify changes, so I made assumptions about the intended minimum wage changes;
there may be misinterpretations on my part.

### Data Source

This dataset is transcribed from these files specifically:

- [ตารางแสดงอัตราค่าจ้างขั้นต่ำและการบังคับใช้ (ตั้งแต่ พ.ศ. 2516 - 2565)](https://www.mol.go.th/wp-content/uploads/sites/2/2022/09/TableWage2016-now_for1Oct2022.xlsx)
- [ประกาศคณะกรรมการค่าจ้างเรื่อง อัตราค่าจ้างขั้นต่ำ (ฉบับที่ 12) และคำชี้แจง พร้อมตารางแสดงอัตราค่าจ้างขั้นต่ำ](https://www.mol.go.th/wp-content/uploads/sites/2/2024/01/%E0%B8%9B%E0%B8%A3%E0%B8%B0%E0%B8%81%E0%B8%B2%E0%B8%A8%E0%B8%84%E0%B8%93%E0%B8%B0%E0%B8%81%E0%B8%A3%E0%B8%A3%E0%B8%A1%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%84%E0%B9%88%E0%B8%B2%E0%B8%88%E0%B9%89%E0%B8%B2%E0%B8%87%E0%B8%82%E0%B8%B1%E0%B9%89%E0%B8%99%E0%B8%95%E0%B9%88%E0%B8%B3-%E0%B8%89.12.pdf)
- [ประกาศคณะกรรมการค่าจ้าง เรื่อง อัตราค่าจ้างขั้นต่ำ (ฉบับที่ 13) และคำชี้แจง พร้อมตารางแสดงอัตราค่าจ้างขั้นต่ำ](https://www.mol.go.th/wp-content/uploads/sites/2/2024/12/%E0%B8%9B%E0%B8%A3%E0%B8%B0%E0%B8%81%E0%B8%B2%E0%B8%A8%E0%B8%84%E0%B9%88%E0%B8%B2%E0%B8%88%E0%B9%89%E0%B8%B2%E0%B8%87%E0%B8%82%E0%B8%B1%E0%B9%89%E0%B8%99%E0%B8%95%E0%B9%88%E0%B8%B3-%E0%B8%8913%E0%B8%A3%E0%B8%B2%E0%B8%8A%E0%B8%81%E0%B8%B4%E0%B8%88%E0%B8%88%E0%B8%B2.pdf)
- [ประกาศคณะกรรมการค่าจ้าง เรื่อง อัตราค่าจ้างขั้นต่ำ (ฉบับที่ 14) และคำชี้แจง พร้อมตารางแสดงอัตราค่าจ้างขั้นต่ำ](https://www.mol.go.th/wp-content/uploads/sites/2/2025/07/%E0%B8%9B%E0%B8%A3%E0%B8%B0%E0%B8%81%E0%B8%B2%E0%B8%A8-%E0%B8%84%E0%B8%88.%E0%B8%82%E0%B8%B1%E0%B9%89%E0%B8%99%E0%B8%95%E0%B9%88%E0%B8%B3-%E0%B8%8914-%E0%B8%A3%E0%B8%A7%E0%B8%A1.pdf)

### Contributing
If you notice any errors or if there are new updates to the data, feel free to open a pull request.
Please describe any changes, and provide links to the supporting documents where possible.

-----

# ชุดข้อมูลอัตราค่าแรงขั้นต่ำประเทศไทย

ชุดข้อมูลนี้ได้ถูกแปลงมาจากข้อมูลของ[กระทรวงแรงงาน](https://www.mol.go.th/%E0%B8%AD%E0%B8%B1%E0%B8%95%E0%B8%A3%E0%B8%B2%E0%B8%84%E0%B9%88%E0%B8%B2%E0%B8%88%E0%B9%89%E0%B8%B2%E0%B8%87%E0%B8%82%E0%B8%B1%E0%B9%89%E0%B8%99%E0%B8%95%E0%B9%88%E0%B8%B3)
ผมได้ทำการแปลงรูปแบบจากไฟล์ Excel / PDF ประกาศจริง เปลี่ยนเป็นไฟล์ CSV เพื่อให้ใช้งานได้ง่ายขึ้นสำหรับงาน data sci ทั้งหลาย

![Data Example](assets/example_data.png)
![Chart Example](assets/example_chart.png)

### การใช้งาน

- ข้อมูลจะเก็บอยู่ในไฟล์ `minimum-wage-by-province.csv`
- คอลัมน์ 1-2 คือชื่อกระทรวงที่ประกาศและฉบับของประกาศ (เขียนตามรูปแบบที่ระบุไว้โดยกระทรวงแรงงาน)
- คอลัมน์ 3 `announce` คือวันประกาศฉบับนั้นๆ เป็นรูปแบบปี พ.ศ. ปี-เดือน-วัน
- คอลัมน์ 4 `effective` คือวันที่ประกาศมีผลบังคับใช้ เป็นรูปแบบปี พ.ศ. ปี-เดือน-วัน
- คอลัมน์ที่เหลือคืออัตรค่าแรงขั้นต่ำ เป็นรายจังหวัด หัวคอลัมน์จะใช้ชื่อจังหวัดนั้นๆเป็นภาษาไทย เช่น `กรุงเทพมหานคร,กระบี่,กาญจนบุรี...` เรียงตามตัวอักษร ก-ฮ
- แต่ละช่องในตารางคืออัตราค่าแรงขั้นต่ำใหม่ แบ่งตามจังหวัด (คอลัมน์) และตามกรม/ฉบับที่ประกาศ (บรรทัด)
- จังหวัดไหนที่ไม่ได้เดี๋ยวข้องกับประกาศนั้นๆ ช่องตารางก็จะถูกปล่อยว่างไว้

### หมายเหตุ

ชุดข้อมูลนี้บันทึกเฉพาะอัตราค่าแรงขั้นต่ำในระดับจังหวัดเท่านั้น
ถ้ามีการประกาศอัตราค่าแรงขั้นต่ำโดยแบ่งตามวิธีอื่น เช่น รายอำเภอ รายอาชีพ หรืออุตสาหกรรม
ชุดข้อมูลนี้จะไม่สามารถระบุความเปลี่ยนแปลงไว้ได้

- กรณีที่มีการระบุค่าแรงขั้นต่ำรายอำเภอ ผมจะเลือกใช้ค่าแรงขั้นต่ำที่น้อยที่สุดเป็นตัวแทนของจังหวัดนั้นๆ
- กรณีที่มีการระบุค่าแรงขั้นต่ำรายอาชีพ หรือตามวิธีอื่นๆ ผมจะไม่เอาการเปลี่ยนแปลงนั้นใส่ไปในชุดข้อมูล

ตัวอย่างจากสองกรณีล่าสุดคือ
- [ประกาศคณะกรรมการค่าจ้าง ฉบับที่ 13 (1 ม.ค. 2568)](https://www.mol.go.th/wp-content/uploads/sites/2/2024/12/%E0%B8%9B%E0%B8%A3%E0%B8%B0%E0%B8%81%E0%B8%B2%E0%B8%A8%E0%B8%84%E0%B9%88%E0%B8%B2%E0%B8%88%E0%B9%89%E0%B8%B2%E0%B8%87%E0%B8%82%E0%B8%B1%E0%B9%89%E0%B8%99%E0%B8%95%E0%B9%88%E0%B8%B3-%E0%B8%8913%E0%B8%A3%E0%B8%B2%E0%B8%8A%E0%B8%81%E0%B8%B4%E0%B8%88%E0%B8%88%E0%B8%B2.pdf) - มีการกำหนดค่าแรงขั้นต่ำระดับอำเภอใน เชียงใหม่ สุราษฎร์ฐานี และสงขลา
- [ประกาศคณะกรรมการค่าจ้าง ฉบับที่ 14 (1 ก.ค. 2568)](https://www.mol.go.th/wp-content/uploads/sites/2/2025/07/%E0%B8%9B%E0%B8%A3%E0%B8%B0%E0%B8%81%E0%B8%B2%E0%B8%A8-%E0%B8%84%E0%B8%88.%E0%B8%82%E0%B8%B1%E0%B9%89%E0%B8%99%E0%B8%95%E0%B9%88%E0%B8%B3-%E0%B8%8914-%E0%B8%A3%E0%B8%A7%E0%B8%A1.pdf) - มีการกำหนดค่าแรงขั้นต่ำระดับอำเภอใน เชียงใหม่ สุราษฎร์ฐานี สงขลา และค่าแรงขั้นต่ำสำหรับกิจการโรงแรมทั่วประเทศ

ประกาศชุดเก่าๆ ที่ไม่ได้มาจากกระทรวงแรงงาน (เช่นประกาศกระทรวงมหาดไทย) ผมไม่สามารถหาเอกสารตัวเดิมมาอ่านได้ ทำได้แค่อิงตามไฟล์ Excel ของกระทรวงแรงงานเอง
ซึ่งบางครั้งจะมีความกำกวมในหมายเหตุ ไม่แน่ใจว่ารวมหรือไม่รวมจังหวัดไหนบ้าง
แปลว่าชุดข้อมูลชุดนี้อาจจะมีความผิดพลาดได้ ตามความเข้าใจของผมเอง

### แหล่งข้อมูล

ข้อมูลชุดนี้ถูกแปลงออกมาจากไฟล์ต่อไปนี้

- [ตารางแสดงอัตราค่าจ้างขั้นต่ำและการบังคับใช้ (ตั้งแต่ พ.ศ. 2516 - 2565)](https://www.mol.go.th/wp-content/uploads/sites/2/2022/09/TableWage2016-now_for1Oct2022.xlsx)
- [ประกาศคณะกรรมการค่าจ้างเรื่อง อัตราค่าจ้างขั้นต่ำ (ฉบับที่ 12) และคำชี้แจง พร้อมตารางแสดงอัตราค่าจ้างขั้นต่ำ](https://www.mol.go.th/wp-content/uploads/sites/2/2024/01/%E0%B8%9B%E0%B8%A3%E0%B8%B0%E0%B8%81%E0%B8%B2%E0%B8%A8%E0%B8%84%E0%B8%93%E0%B8%B0%E0%B8%81%E0%B8%A3%E0%B8%A3%E0%B8%A1%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%84%E0%B9%88%E0%B8%B2%E0%B8%88%E0%B9%89%E0%B8%B2%E0%B8%87%E0%B8%82%E0%B8%B1%E0%B9%89%E0%B8%99%E0%B8%95%E0%B9%88%E0%B8%B3-%E0%B8%89.12.pdf)
- [ประกาศคณะกรรมการค่าจ้าง เรื่อง อัตราค่าจ้างขั้นต่ำ (ฉบับที่ 13) และคำชี้แจง พร้อมตารางแสดงอัตราค่าจ้างขั้นต่ำ](https://www.mol.go.th/wp-content/uploads/sites/2/2024/12/%E0%B8%9B%E0%B8%A3%E0%B8%B0%E0%B8%81%E0%B8%B2%E0%B8%A8%E0%B8%84%E0%B9%88%E0%B8%B2%E0%B8%88%E0%B9%89%E0%B8%B2%E0%B8%87%E0%B8%82%E0%B8%B1%E0%B9%89%E0%B8%99%E0%B8%95%E0%B9%88%E0%B8%B3-%E0%B8%8913%E0%B8%A3%E0%B8%B2%E0%B8%8A%E0%B8%81%E0%B8%B4%E0%B8%88%E0%B8%88%E0%B8%B2.pdf)
- [ประกาศคณะกรรมการค่าจ้าง เรื่อง อัตราค่าจ้างขั้นต่ำ (ฉบับที่ 14) และคำชี้แจง พร้อมตารางแสดงอัตราค่าจ้างขั้นต่ำ](https://www.mol.go.th/wp-content/uploads/sites/2/2025/07/%E0%B8%9B%E0%B8%A3%E0%B8%B0%E0%B8%81%E0%B8%B2%E0%B8%A8-%E0%B8%84%E0%B8%88.%E0%B8%82%E0%B8%B1%E0%B9%89%E0%B8%99%E0%B8%95%E0%B9%88%E0%B8%B3-%E0%B8%8914-%E0%B8%A3%E0%B8%A7%E0%B8%A1.pdf)

### สนับสนุนงาน
ถ้าต้องการช่วยซัพพอร์ทงานนี้ แก้ไขข้อมูลผิด อัพเดทข้อมูลใหม่ สามารถเปิดเป็น pull request ใหม่ให้ได้เลยครับ
รบกวนอธิบายเรื่องที่แก้ และแนบลิงค์เอกสารมาเป็นหลักฐานด้วย ขอบคุณครับ