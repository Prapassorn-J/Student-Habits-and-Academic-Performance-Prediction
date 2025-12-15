# Student Habits and Academic Performance Prediction
DSI311 – Data Science Algorithms (Final Project)

  โครงงานนี้มุ่งเน้นการวิเคราะห์ข้อมูลเชิงลึกเกี่ยวกับ พฤติกรรมการเรียนและการใช้ชีวิตของนักเรียน เพื่อสร้างแบบจำลองทำนาย ผลสัมฤทธิ์ทางการเรียน (Exam Score) โดยใช้เทคนิค Regression และ Machine Learning พร้อมทั้งอธิบายความสัมพันธ์ของปัจจัยต่าง ๆ ในเชิงข้อมูลอย่างเป็นระบบ

  โครงงานถูกออกแบบตามกระบวนการทำงานจริงของสาย Data ได้แก่
Data Cleaning → Feature Engineering → Feature Selection → Modeling → Evaluation

# Problem Statement

  พฤติกรรมในชีวิตประจำวันของนักเรียน เช่น ชั่วโมงอ่านหนังสือ การนอน การใช้สื่อออนไลน์ และสุขภาพจิต
มีผลต่อผลการเรียนมากน้อยเพียงใด และปัจจัยใดส่งผลอย่างมีนัยสำคัญที่สุด?

โครงงานนี้จึงมีเป้าหมายเพื่อ:
-วิเคราะห์ความสัมพันธ์เชิงข้อมูลระหว่างพฤติกรรมและคะแนนสอบ

-สร้างโมเดลที่สามารถทำนายผลการเรียนได้อย่างแม่นยำ

-ตีความผลลัพธ์เพื่อใช้เป็นแนวทางในการพัฒนาพฤติกรรมการเรียนในอนาคต

# Objectives

-วิเคราะห์ปัจจัยด้านพฤติกรรม สุขภาพ และไลฟ์สไตล์ที่ส่งผลต่อผลการเรียน

-สร้างและเปรียบเทียบโมเดล Regression หลายรูปแบบ

-คัดเลือก Feature ที่สำคัญเพื่อลดความซับซ้อนของโมเดล

-ประเมินโมเดลด้วยตัวชี้วัดมาตรฐาน (MAE, RMSE, R²)

# Dataset

-Student Habits vs Academic Performance (Kaggle)

-ข้อมูลเริ่มต้น: 1,000 records

-หลังทำความสะอาด: 909 records

-ตัวแปรรวม: 16 features

    -พฤติกรรมการเรียน (Study hours, Attendance)
    
    -การใช้สื่อดิจิทัล (Social media, Netflix)
    
    -สุขภาพ (Sleep hours, Mental health, Exercise)
    
    -พื้นฐานครอบครัวและสิ่งแวดล้อม

# Methodology

1️⃣ Data Cleaning & Preprocessing

-ตรวจสอบและจัดการ Missing Values และ Duplicate Data

-แปลงตัวแปรเชิงหมวดหมู่ด้วย One-Hot Encoding

-ปรับสเกลข้อมูลด้วย StandardScaler

-ตรวจสอบ Outliers และความเหมาะสมของข้อมูลก่อนสร้างโมเดล

2️⃣ Feature Engineering

สร้าง Feature เชิงพฤติกรรมเพื่อสะท้อนภาพรวมการใช้ชีวิตของนักเรียน เช่น:

-total_screen_time → เวลาหน้าจอรวม

-study_sleep_ratio → ความสมดุลระหว่างการเรียนและการพักผ่อน

-is_parent_high_edu → ตัวชี้วัดสภาพแวดล้อมทางการศึกษา

3️⃣ Feature Selection

-ใช้ SelectKBest (f_regression)

-คัดเลือก Feature ที่มีความสัมพันธ์กับคะแนนสอบสูงสุด

-ลด Noise และลดความเสี่ยงของ Overfitting

4️⃣ Modeling

พัฒนาและเปรียบเทียบโมเดล Regression จำนวน 4 โมเดล:

-Multiple Linear Regression

-Ridge Regression

-Lasso Regression

-Random Forest Regression

ใช้ 5-Fold Cross Validation เพื่อให้การประเมินผลมีความน่าเชื่อถือ

5️⃣ Evaluation

ประเมินโมเดลด้วย:

-Mean Absolute Error (MAE)

-Root Mean Squared Error (RMSE)

-R² Score

พร้อมเปรียบเทียบผลระหว่าง Train/Test เพื่อวิเคราะห์ความเสถียรของโมเดล

# Key Results

-โมเดลเชิงเส้น (Linear / Ridge / Lasso) ให้ผลลัพธ์ดีที่สุด

    -R² (Test) ≈ 0.89
    
-โมเดลไม่มีปัญหา Overfitting (Train/Test performance ใกล้เคียงกัน)

-Feature ที่ส่งผลต่อคะแนนสอบมากที่สุด ได้แก่:

    -ชั่วโมงอ่านหนังสือ
    
    -ความสมดุลระหว่างการเรียนและการพักผ่อน

    -สุขภาพจิต
    
    -เวลาใช้สื่อดิจิทัล
    
    -การออกกำลังกาย และการเข้าเรียน

# Insights & Takeaways

-พฤติกรรมการเรียนที่มีประสิทธิภาพไม่ได้ขึ้นกับ “อ่านเยอะ” เพียงอย่างเดียว

แต่ขึ้นกับ สมดุลของการเรียน การพักผ่อน และสุขภาพจิต

-Feature Engineering มีบทบาทสำคัญในการเพิ่มคุณภาพของโมเดล

-Regression Models สามารถอธิบายความสัมพันธ์ของข้อมูลเชิงพฤติกรรมได้ดีและตีความได้ชัดเจน

# Tools & Technologies

-Python (Pandas, NumPy)

-Scikit-learn

-Matplotlib, Seaborn

-Jupyter Notebook / Google Colab
