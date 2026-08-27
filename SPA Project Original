print('============================')
print('STUDENT PERFORMANCE ANALYZER')
print('============================')

name = input('Enter your name: ')

print('\n--- GRADING SYSTEM ---')

while True:
    try:
        minimum_grade=float(input('What is the minimum possible grade? '))
        break
    except ValueError:
        print('Invalid input. Please enter a number.')
    
while True:
    try:
        maximum_grade=float(input('What is the maximum possible grade? '))
        
        if maximum_grade <= minimum_grade:
            print('Invalid input. The maximum grade must be greater than the minimum grade.')
        else:
            break
    except ValueError:
        print('Invalid input. Please enter a number.')

grades= {}

while True:
    try:
        number_of_subjects= int(input('How many subjects do you want to enter? '))
        
        if number_of_subjects < 1:
            print('Invalid input. Please enter at least 1 subject.')
        else:
            break
            
    except ValueError:
        print('Invalid input. Please enter a whole number.')
        
print('\n--- SUBJECT RESULTS ---')

for i in range(number_of_subjects):
    subject= input('Enter the subject name: ')
    
    while True:   
        if subject.strip() == '':
            print('Invalid input. Please enter a subject name.')
      
        elif subject in grades:
            print('Invalid input. Please enter a different subject.')
        
        else:
            break
    
        subject= input('Enter the subject name: ')

    while True:
        try:
            grade= float(input('Enter the grade: '))
        
            if grade < minimum_grade or grade > maximum_grade:
                print('Invalid input. Please enter a grade within the specified range.')
            else:
                break
        
        except ValueError:
            print('Invalid input. Please enter a number.')
    subject = subject.strip()
    grades[subject]= grade

print('\n--- AVERAGE GRADE CALCULATION ---')

#Calculate average
total= sum(grades.values())
average= total / len(grades)
performance_percentage= ((average - minimum_grade) / (maximum_grade - minimum_grade))*100
if performance_percentage >= 90:
    performance= 'Excellent'
elif performance_percentage >= 80:
    performance= 'Very Good'
elif performance_percentage >= 70:
    performance= 'Good'
elif performance_percentage >= 60:
    performance= 'Satisfactory'
else:
    performance= 'Needs Improvement'
    
print(f'Your average grade is: {average:.2f}')

#Find strongest and weakest subjects 
strongest_subject= max(grades, key=grades.get)
weakest_subject= min(grades, key=grades.get)

print('Your strongest subject is:', strongest_subject)
print('Your weakest subject is:', weakest_subject)

#Performance Statistics 
highest_grade= max(grades.values())
lowest_grade= min(grades.values())

print('PERFORMANCE STATISTICS')
print('======================')
print(f'Average grade: {average:.2f}')
print(f'Highest grade: {highest_grade:.2f}')
print(f'Lowest grade: {lowest_grade:.2f}')
print(f'Number of subjects: {len(grades)}')
print('-------------------------------------')
print(f'Overall performance: {performance}\n ')
print('========================================')

print('\n--- TARGET AVERAGE ---')

#Desired average
while True:
    try:
        desired_average= float(input('What average would you like to achieve? ')) 
    
        if desired_average > maximum_grade or desired_average < minimum_grade:
            print('Invalid Input. Please enter a grade within the grading range.')
        else: 
            break
    except ValueError:
        print('Invalid input. Please enter a number.')
if desired_average <= average:
    print('You have already achieved your desired average.')
else: 
    required_grade= (desired_average * (len(grades) + 1 )) - total
    
    if required_grade > maximum_grade:
        print('This target is not achievable because the maximum grade is', f'{maximum_grade:.2f}')
    
    elif required_grade < minimum_grade:
        print('You will achieve your desired average even with the minimum grade of', f'{minimum_grade:.2f}')
   
    else:
        print('You need a grade of', f'{required_grade:.2f}', 'on your next subject.')
        
print('\n--- ACADEMIC PERFORMANCE SUMMARY ---')       
        
# Brief Academic Performance Report

with open('student_data.txt', 'w') as file:
    file.write('==============================\n')
    file.write('ACADEMIC PERFORMANCE REPORT\n')
    file.write('==============================\n')
    file.write(f'Student: {name}\n')
    file.write(f'Grading range: {minimum_grade:.2f} - {maximum_grade:.2f}\n')
    file.write('\n')
    
    file.write('SUBJECT RESULTS\n')
    file.write('---------------\n')
    
    for subject, grade in grades.items():
        file.write(f'{subject}: {grade:.2f}\n')
        
    file.write('\n')
    file.write('PERFORMANCE SUMMARY\n')
    file.write('-------------------\n')
    file.write(f'Average grade: {average:.2f}\n')
    file.write(f'Performance percentage: {performance_percentage:.2f}%\n')
    file.write(f'Strongest subject: {strongest_subject}\n')
    file.write(f'Weakest subject: {weakest_subject}\n')
    file.write(f'Highest grade: {highest_grade:.2f}\n')
    file.write(f'Lowest grade: {lowest_grade:.2f}\n')
    file.write(f'Number of subjects: {len(grades)}\n')
    file.write(f'Overall performance: {performance}\n')
    file.write('===========================================')
        
print('\nYour academic performance report has been saved successfully.')
print('Report saved as: student_data.txt')

        
