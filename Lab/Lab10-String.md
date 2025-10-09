## โจทย์

จงเขียนโปรแกรมเพื่อรับคำจากผู้ใช้งาน เพื่อตรวจสอบว่า คำที่กรอกมามีลักษณะเป็นคำหรือวลีที่สามารถอ่านจากหลังไปหน้าหรือหน้าไปหลังแล้วยังคงความหมายเหมือนเดิมได้ โดยที่ หากคำนั้นสามารถอ่านจากหน้าไปหลังหรือหลังไปได้ ให้แสดงผลลัพธ์ว่า Pass แต่หากทำไม่ได้ให้ขึ้นว่า Not Pass


## FIX CODE
```c++
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char text[100];
    int i, j, length;
    int isPalindrome = 1; // ตั้งค่าเริ่มต้นว่าเป็น palindrome

    printf("Enter word : ");
    gets(text); // รับข้อความจากผู้ใช้ (คำเตือน: ใช้ได้เฉพาะในงานเรียนรู้พื้นฐาน)

    // ลบช่องว่างและเปลี่ยนเป็นตัวพิมพ์เล็กทั้งหมด
    char cleaned[100];
    int k = 0;
    for (i = 0; text[i] != '\0'; i++) {
        if (isalnum(text[i])) { // รับเฉพาะตัวอักษรและตัวเลข
            cleaned[k++] = tolower(text[i]);
        }
    }
    cleaned[k] = '\0';

    length = strlen(cleaned);

    // ตรวจสอบจากต้นและปลาย
    for (i = 0, j = length - 1; i < j; i++, j--) {
        if (cleaned[i] != cleaned[j]) {
            isPalindrome = 0;
            break;
        }
    }

    if (isPalindrome)
        printf("Pass\n");
    else
        printf("Not Pass\n");

    return 0;
}

```

## TEST CASE
### Input
```bash
Enter word:
radar
```
### Output
```bash
Pass.
```

## TEST CASE
### Input
```bash
Enter word:
hello
```
### Output
```bash
Not Pass.
```

## TEST CASE
### Input
```bash
Enter word:
Radar
```
### Output
```bash
Pass.
```

## TEST CASE
### Input
```bash
Enter word:
here
```
### Output
```bash
Not Pass.
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
