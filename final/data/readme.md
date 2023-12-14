

#### MovieLens 100k Dataset Overview for Our Project

In our movie recommendation system, we utilized the MovieLens 100k dataset, focusing on user watch histories and their subsequent movie choices. This dataset is a collection of 100,000 movie ratings from 943 users, but for our specific application, we concentrated on the following aspects:

1. **Watched Movies**: Each user's list of watched movies, which serves as the primary input for analyzing user preferences and predicting future interests. This list is crucial for both training our baseline models and formulating prompts for the GPT-3.5 and GPT-4 models.

2. **Next Watched Movie**: The next movie watched by each user, which we used as a key measure for evaluating the accuracy of our recommendation models. The success of a recommendation is determined by its presence in the user's subsequent viewing.

For instance, we randomly selected user lists from the dataset to illustrate the data structure:

```python
# Example Python code for selecting and displaying user lists
num_lists_to_select = 20
selected_user_lists = random.sample(data_ml_100k, num_lists_to_select)

for i, user_list in enumerate(selected_user_lists, start=1):
    print(f"Example {i}:")
    print("Watched Movies:", user_list[0])
    print("Next Watched Movie:", user_list[1])
    print("\n")
```
Output :
```
Example 1:
Watched Movies: The Thin Man | Ran | Dumbo | James and the Giant Peach | 2001: A Space Odyssey | Belle de jour | Terminator 2: Judgment Day | French Twist (Gazon maudit) | Three Colors: Red | Casino | The Hunchback of Notre Dame | The Specialist | Home Alone | Bedknobs and Broomsticks | Pink Floyd - The Wall | Beauty and the Beast | The Love Bug | Mr. Holland's Opus | Star Trek: The Wrath of Khan | Picture Bride | Annie Hall | Toy Story | Gone with the Wind | Fargo | Like Water For Chocolate (Como agua para chocolate) | The Preacher's Wife | 101 Dalmatians | Willy Wonka and the Chocolate Factory | Swingers | Looking for Richard | Surviving Picasso | Twelfth Night | Bound | The Island of Dr. Moreau | Emma | Ransom | The Adventures of Pinocchio | Lone Star | Wild Things | The Postman | Titanic | The Apostle | Eve's Bayou | The Devil's Advocate | Fly Away Home | I Know What You Did Last Summer | Chasing Amy | Ulee's Gold | Kiss Me, Guido | George of the Jungle
Next Watched Movie: Liar Liar


Example 2:
Watched Movies: Legal Deceit | Deconstructing Harry | The English Patient | Amistad | Good Will Hunting | Air Force One | Washington Square | Apt Pupil | Blues Brothers 2000 | L.A. Confidential | The Wings of the Dove | The Full Monty | Mouse Hunt | Little City | Cop Land | The Rainmaker | Shooting Fish | Boogie Nights | Titanic | The Man Who Knew Too Little | Gattaca | Seven Years in Tibet | Welcome To Sarajevo | The Truman Show | The Jackal | The Postman | The Apostle | The Replacement Killers | The Devil's Advocate
Next Watched Movie: Wag the Dog


Example 3:
Watched Movies: Scream | The Devil's Advocate | Liar Liar | Dante's Peak | Murder at 1600 | The Devil's Own | Half Baked | Spawn | Chasing Amy | Air Force One | The English Patient | Free Willy 3: The Rescue | The Saint | Volcano | McHale's Navy | Evita | Jungle2Jungle | Mouse Hunt | The Prophecy II | The Beautician and the Beast | House Arrest | Ransom | Courage Under Fire | Star Trek: First Contact | The People vs. Larry Flynt | Twelve Monkeys | The Rock | Gridlock'd | Bound | Toy Story | The Ghost and the Darkness | The Spitfire Grill | Postino, Il | Trainspotting | Jane Eyre | Fierce Creatures | That Thing You Do! | Mystery Science Theater 3000: The Movie | Mission: Impossible | Jerry Maguire | Swingers | Willy Wonka and the Chocolate Factory | Beavis and Butt-head Do America | 2 Days in the Valley | Mother Night | Jackie Chan's First Strike | Ghost in the Shell (Kokaku kidotai) | The Nightmare Before Christmas
Next Watched Movie: Heavy Metal
```
