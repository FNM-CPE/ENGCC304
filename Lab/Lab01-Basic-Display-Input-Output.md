## โจทย์
จงแก้ไขโค้ดต่อไปนี้ ให้สามารถรับค่าจากผู้ใช้ เพื่อแสดงผลบนหน้าจอคอมพิวเตอร์ให้ได้ พร้อมทั้งจัดรูปแบบให้ตรงตาม Syntax ที่เรียนมาในห้องเรียน

```c++
#include <stduio.h>

int main() {
    char Name[50] ;
    int  Age = 0 ;
    printf( "Enter your name: " ) 
    scanf( "%s", Name ) ;
    printf( "Enter your age: " ) ;
    scanf( "%d", Age ) ;
    print( "- - - - - -\n" ) ;
    printf( "Hello %s \n", ___ ) ; 
    printf( "Age = %d\n", ___ ) ; 
    
}//end main function
```

## FIX CODE
```c++
#include <stdio.h>

int main() {
    char Name[50] ;
    int  Age = 0 ;
    printf( "Enter your name: " ) ;
    scanf( "%s", &Name ) ;
    printf( "Enter your age: " ) ;
    scanf( "%d", &Age ) ;

    printf( "- - - - - -\n" ) ;
    printf( "Hello %s \n", Name ) ; 
    printf( "Age = %d\n", Age ) ; 

    return 0;
    
}//end main function
```

## TEST CASE
### Input
```bash
Enter your name: Nattawat
Enter you age: 18

```
<img width="160" alt="Screenshot 2025-07-03 183206" src="https://github.com/user-attachments/assets/c93f33eb-67ef-42a2-bb5f-3ae1ba310c00" />
### Output
```bash
- - - - - -
Hello Natthawat
Age = 18
<img width="100" alt="Screenshot 2025-07-03 183220" src="https://github.com/user-attachments/assets/036a9a21-5ff3-4285-ad8e-dd0d41c788d1" />

```

## มาตรฐานการตรวจตามหลักการเรียนรู้ของบลูม
| ลำดับการเรียนรู้ | เกณฑ์การวัด | คะแนน |
| -------- | -------- | -------- |
| รู้จำ | เห็นโครงสร้างของโค้ดโปรแกรมชัดเจน ได้มาตรฐาน | 1 pts |
| เข้าใจ | แก้ไขปัญหาได้ตามที่โจทย์กำหนด | 1 pts |
| ประยุกต์ใช้ | สามารถผ่านเงื่อนไขได้ทุก testcase | 1 pts |
| วิเคราะห์ | หาจุดผิดของโปรแกรมได้ | 1 pts |
| ประเมินค่า | โปรแกรมเสร็จสมบูรณ์ระยะเวลาที่กำหนด | 1 pts |
| สร้างสรรค์ | แก้ไขสถานการณ์ของโจทย์ | 1 pts |
||<p style='text-align: right !important;'>**รวม**</p>|**6 pts**|
