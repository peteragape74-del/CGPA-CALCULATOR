# CGPA-CALCULATOR
A python made CGPA calculator

total_credit_hours = 0
total_weighted_grade_points = 0

num_courses_str = input("Enter the number of courses: ")
num_courses = int(num_courses_str)

# Loop through each course to get details
current_course = 0
while current_course < num_courses:
    print("\n--- Course " + str(current_course + 1) + " ---")
    
    credit_hours_str = input("Enter credit hours for this course: ")
    credit_hours = float(credit_hours_str)
    
    grade_letter = input("Enter grade (A, B, C, D, F) for this course: ").upper()
    
    grade_point = 0.0
    if grade_letter == 'A':
        grade_point = 5.0
    elif grade_letter == 'B':
        grade_point = 4.0
    elif grade_letter == 'C':
        grade_point = 3.0
    elif grade_letter == 'D':
        grade_point = 2.0
    elif grade_letter == 'F':
        grade_point = 0.0
    else:
        print("Invalid grade entered. Assuming F (0.0 points).")
        grade_point = 0.0
        
    total_credit_hours = total_credit_hours + credit_hours
    total_weighted_grade_points = total_weighted_grade_points + (credit_hours * grade_point)
    
    current_course = current_course + 1

# Calculate CGPA
if total_credit_hours > 0:
    cgpa = total_weighted_grade_points / total_credit_hours
    print("\n------------------------------------")
    print("Your calculated CGPA is: " + str(round(cgpa, 2)))
else:
    print("\nNo courses entered or total credit hours are zero. Cannot calculate CGPA.")
