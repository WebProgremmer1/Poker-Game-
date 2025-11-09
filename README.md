# Poker-Game-
Python project showing insertion sort in playtful way with using cards concept 

# Algorithm Name
Insertion Algorithm 
## Demo video/gif/screenshot of test
https://github.com/user-attachments/assets/310ad20c-eaeb-43d4-a5ee-8d86ab988259
https://github.com/WebProgremmer1/Poker-Game-/blob/d912586a8906c3f5aca23eb76ce86b44e6f19420/test.png
![image alt](https://github.com/WebProgremmer1/Poker-Game-/blob/d912586a8906c3f5aca23eb76ce86b44e6f19420/test.png)
## Problem Breakdown & Computational Thinking (You can add a flowchart and write the
four pillars of computational thinking briefly in bullets)

**Decomposition: 
The first element + 1 compares with the first element. If the first element is bigger than the next one, it swaps. If the second is smaller than it stays on its position. In both ways, we repeat the process but with the next elements. We compare the third element with second if smaller than with first. If not, it stays on position between previous first and second position.  The process repeats until the list is sorted. 
**Pattern Recognition:
Repeating process, if the element is higher it swaps, if the element is smaller than it stay unchanged.
**Abstraction:
The user should see how we choose the elements and swap them. If we do not swap card, it means that the chosen element is smaller and we do not change anything. My plan is to highlight the card which we compare and the previous element. Each comparison highlights the more deep understanding of the user and make it more interesting to watch.  The process of randomizing the cards and changing after 10 elements to ‘J’, ‘Q’, ‘K’ and ‘A’ are not shown to the user. 
**Algorithm Design:
Input: The input is number from 1 to 52 because in the desk there is only 52 cards in the desk, and obviously we cannot choose 0 cards. What is the point to shuffle 0 cards. 
Processing: The first step is to check if the input satisfies our condition. This number is really from range 1 to 52. The second step is randomizing amount of cards that user put into program.  The third step is to use a sorting algorithm to sort the numbers from smallest to highest. The fourth step is to add suit to the card. I have shown backend part. 
In case of Gradio implementation, the user sees unsorted cards in the array way. The program is showing sort process in the real time. 
**Flowcharts
https://github.com/WebProgremmer1/Poker-Game-/blob/d912586a8906c3f5aca23eb76ce86b44e6f19420/flowchart1.png
https://github.com/WebProgremmer1/Poker-Game-/blob/d912586a8906c3f5aca23eb76ce86b44e6f19420/flowchart2.png
https://github.com/WebProgremmer1/Poker-Game-/blob/d912586a8906c3f5aca23eb76ce86b44e6f19420/flowchart3.png
https://github.com/WebProgremmer1/Poker-Game-/blob/d912586a8906c3f5aca23eb76ce86b44e6f19420/flowchart4.png
## Steps to Run
Local run: Copy link http://127.0.0.1:7860. The program will be opened in the browser. User can choose to manage enter number in range of 1 to 52. Also, user can manage step dalay from 0 to 600 ms. Program will generate some amount of cards and user can tap icon of full screen. It will open cards in full screen format. 
## Hugging Face Link
https://huggingface.co/spaces/HeyPeople2025/Poker_Game
## Author & Acknowledgment
I decided to present this project in cards format because I think it is really cool implementation. It makes the program more engaging and entertainment then I would present Insertion Sort as lists. 
