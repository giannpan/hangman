def printing(b):
    for j in range (len(b)):
        print(b[j], end = '')
    print('')


def hang (a):
    if a == 1:
        print('_______ \n|     |  \n|     Ο \n|        \n|       \n|        \n| ')
    elif a==2:    
        print('_______ \n|     |  \n|     Ο \n|     |  \n|       \n|        \n| ')
    elif a==3:
        print('_______ \n|     |  \n|     Ο \n|    /|  \n|       \n|        \n| ')
    elif a==4:
        print('_______ \n|     |  \n|     Ο \n|    /|\ \n|       \n|        \n| ')
    elif a==5:
        print('_______ \n|     |  \n|     Ο \n|    /|\ \n|     | \n|    /   \n| ')
    else:
        print('_______ \n|     |  \n|     Ο \n|    /|\ \n|     | \n|    / \ \n| ')



import random
hw = [['Κ', 'Υ', 'Μ', 'Α'],['Θ', 'Α', 'Λ', 'Α', 'Σ', 'Σ', 'Α'],['Τ', 'Ρ', 'Α', 'Ι', 'Ν', 'Ο'],['Κ', 'Ι', 'Θ', 'Α', 'Ρ', 'Α'],['Κ', 'Ρ', 'Ε', 'Μ', 'Α', 'Λ', 'Α']]
l = random.randint(0,6)
hidden = hw[l]
letters = ['Α' , 'Β' , 'Γ' , 'Δ' , 'Ε' , 'Ζ' , 'Η' , 'Θ' , 'Ι' , 'Κ' , 'Λ' , 'Μ' , 'Ν' , 'Ξ' , 'Ο' , 'Π' , 'Ρ' , 'Σ' , 'Τ' , 'Υ' , 'Φ' , 'Χ' , 'Ψ' , 'Ω']
word = []
already = []
for i in range (len(hidden)):
    word.append('_')
for j in range (len(word)):
    print(word[j], end = '')
tries = 0
while word[:] != hidden[:] and tries<6:    
    x = input('ΔΩΣΕ ΕΝΑ ΕΛΛΗΝΙΚΟ ΚΕΦΑΛΑΙΟ: ')
    if x in letters and x not in word:
        if x in hidden:
            for k in range (len(hidden)):
                if x == hidden[k]:
                    word[k] = hidden[k]
        else:
            tries += 1
            hang(tries)
            already.append(x)
            print('ΕΧΕΙΣ ΑΚΟΜΗ', 6-tries , 'ΠΡΟΣΠΑΘΕΙΕΣ ΜΕΧΡΙ ΝΑ ΧΑΣΕΙΣ')
        printing(word)
        print('ΤΑ ΓΡΑΜΜΑΤΑ ΠΟΥ ΕΧΕΙΣ ΔΩΣΕΙ ΜΕΧΡΙ ΣΤΙΓΜΗΣ ΕΙΝΑΙ: ')
        print(already)
        
    else: 
        print('ΛΑΘΟΣ ΕΠΙΛΟΓΗ! ΞΑΝΑΔΟΚΙΜΑΣΕ!')
else: 
    if tries == 6:
        print('ΔΥΣΤΥΧΩΣ ΕΧΑΣΕΣ! Η ΛΕΞΗ ΗΤΑΝ', end = ' ')
        printing(hidden)
    else:  
        print('ΜΠΡΑΒΟ ΚΕΡΔΙΣΕΣ')


    
