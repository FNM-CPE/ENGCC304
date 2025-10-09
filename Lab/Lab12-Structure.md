## โจทย์
จงเขียนฟังก์ชันการตัดเกรดในแต่ละรายวิชาของนักเรียนจำนวน 3 คน โดยนักเรียนแต่ละคนจะมีข้อมูลดังต่อไปนี้
ชื่อ, นักศักศึกษา, คะแนนในวิชาที่ 1, คะแนนในวิชาที่ 2, คะแนนในวิชาที่ 3, คะแนนในวิชาที่ 4, คะแนนในวิชาที่ 5
แสดงได้ดังโครงสร้างข้อมูลต่อไปนี้

## FIX CODE
```c++
struct Student {
    char Name[20] ;
    char ID[5] ;
    float ScoreSub1 ;
    float ScoreSub2 ;
    float ScoreSub3 ;
    float ScoreSub4 ;
    float ScoreSub5 ;
} typedef S ;

#include <stdio.h>

// โครงสร้างข้อมูลนักเรียน
typedef struct Student {
    char Name[20];
    char ID[5];
    float ScoreSub1;
    float ScoreSub2;
    float ScoreSub3;
    float ScoreSub4;
    float ScoreSub5;
} S;

// ฟังก์ชันคำนวณเกรดจากคะแนน
char grade(float score) {
    if (score >= 80) return 'A';
    else if (score >= 70) return 'B';
    else if (score >= 60) return 'C';
    else if (score >= 50) return 'D';
    else return 'F';
}

// ฟังก์ชันแสดงผลข้อมูลนักเรียนและเกรดแต่ละวิชา
void showGrade(S st) {
    printf("\n----------------------------------\n");
    printf("Name : %s\n", st.Name);
    printf("ID   : %s\n", st.ID);
    printf("Subject 1: %.2f -> Grade %c\n", st.ScoreSub1, grade(st.ScoreSub1));
    printf("Subject 2: %.2f -> Grade %c\n", st.ScoreSub2, grade(st.ScoreSub2));
    printf("Subject 3: %.2f -> Grade %c\n", st.ScoreSub3, grade(st.ScoreSub3));
    printf("Subject 4: %.2f -> Grade %c\n", st.ScoreSub4, grade(st.ScoreSub4));
    printf("Subject 5: %.2f -> Grade %c\n", st.ScoreSub5, grade(st.ScoreSub5));
}

int main() {
    S student[3]; // นักเรียนทั้งหมด 3 คน
    int i;

    printf("=== Input Student Data ===\n");
    for (i = 0; i < 3; i++) {
        printf("\nEnter information for student %d\n", i + 1);
        printf("Name: ");
        scanf(" %[^\n]", student[i].Name);
        printf("ID: ");
        scanf("%s", student[i].ID);
        printf("Enter score for 5 subjects: ");
        scanf("%f %f %f %f %f",
              &student[i].ScoreSub1,
              &student[i].ScoreSub2,
              &student[i].ScoreSub3,
              &student[i].ScoreSub4,
              &student[i].ScoreSub5);
    }

    printf("\n\n=== Student Grades ===\n");
    for (i = 0; i < 3; i++) {
        showGrade(student[i]);
    }

    return 0;
}

```

## TEST CASE
### Input
```bash
Enter the details of 3 students :
Student 1:
Name: 
John Doe
ID: 
101
Scores in Subject 1: 
77
Scores in Subject 2: 
64
Scores in Subject 3: 
66
Scores in Subject 4: 
54
Scores in Subject 5: 
56

Student 2:
Name: 
Jane Smith
ID: 
102
Scores in Subject 1: 
43
Scores in Subject 2: 
70
Scores in Subject 3: 
76
Scores in Subject 4: 
77
Scores in Subject 5: 
80

Student 3:
Name: 
Mark Johnson
ID: 
103
Scores in Subject 1: 
77
Scores in Subject 2: 
74
Scores in Subject 3: 
76
Scores in Subject 4: 
81
Scores in Subject 5: 
69
```
### Output
```bash
Student 1:
Name: John Doe
ID: 101
Scores: 77 64 66 54 56
Grades: B+ C C+ D D+
Average Scores: 63.4

Student 2:
Name: Jane Smith
ID: 102
Scores: 43 70 76 77 80
Grades: F B B+ B+ A
Average Scores: 69.2

Student 3:
Name: Mark Johnson
ID: 103
Scores: 77 74 76 81 69
Grades: B+ B B+ A C+
Average Scores: 75.4
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
