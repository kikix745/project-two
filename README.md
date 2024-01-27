# project-two
def generate_combinations(remaining_letters, current_string, combinations):

    if remaining_letters == 0:
        combinations.append(current_string)
        return

    for i in range(len(current_string) + 1):
        new_string = current_string[:i] + drawn_letters[0] + current_string[i:]
        generate_combinations(remaining_letters - 1, new_string, combinations)

   
    drawn_letters = drawn_letters[1:] + drawn_letters[0]

drawn_letters = "ABC" 
all_combinations = []

for length in range(2, len(drawn_letters) + 1): 
    generate_combinations(length, "", all_combinations)

print(all_combinations)
