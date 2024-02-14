# Find-Winner-Among-Submissions
In the "Concise Insight Contest, " participants showcase their knowledge through brief written pieces. Each participant is given a distinct number ranging from 1 to 𝑛, and they each submit one piece. The length of the 𝑖- th submission is 𝑎𝑖 words, and it is awarded a distinct quality score of 𝑏𝑖. 


def find_winner(n, submissions):
    valid_submissions = [(i+1, a, b) for i, (a, b) in enumerate(submissions) if a <= 10]

    if not valid_submissions:
        return -1  
    winner_id, _, max_quality = max(valid_submissions, key=lambda x: x[2])
    return winner_id

n = int(input())
submissions = [tuple(map(int, input().split())) for _ in range(n)]

result = find_winner(n, submissions)
print(result)
