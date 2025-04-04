
<div align="center">
  <a href="https://github.com/Hermayni/AWD-Xplora-Fuecoco">
    <img src="Xplora-Logo.png" alt="Xplora" width="330" height="300">
  </a>
  <h3 align="center" style="font-size: 25px;">Urban Explorer: Xplora</h3>
</div>

## Persona
<br>

**Name:** Xplora <br>
**Age:** 28 years old <br>
**Background:** <br>
- An urban professional passionate about discovering new neighborhoods, hidden cafes, and local events.

**Key Characteristics:** 
- Adventurous 
- Spontaneous
- Curious
- Passionate


## UX Flow
<ol>

<li> Landing Page</li>

- **Services Offered** Users could see what the website has to offer to them
- **Information about the Webiste** Ussers could learn what the website is all about and what are the goals of making the website.

<li> User Authentication</li>

- **Login/Registration:** Secure sign-in via Authentication.
- **Welcome/Tutorial:** Quick onboarding to highlight app features.

<li> Landing Page:</li>

- **Submit post** user s

<li> Posts Interaction:
</li> 

- **Upvoting and Downvoting of posts:** Users can rate whether the place is a good spot or not.
- **Bookmarking Post:** User can bookmark posts and have it stored in the bookmark tab.


</ol>

## Layout and Navigation

 <li> Navigation Bar

 - **Home:** Featured Hot spots recommended by Xplora.
 - **Spots:** The users can submit posts.
 - **About us:** Learn more about the developers
 - **Log Out button:** Log's the user that is signed in out of the website
</li>

<li>
Screen Layout

- **Home Screen:**  Hero page about information of the website and services offered.
- **Submitted Posts SCreen:**  Scrollable view with texts and interactive review submission.
- **Submit post:** Form layout with input fields and submit button.
- **Category Filters** See sorted out posts based on their categories
</li>
 

 ## Color Scheme and Visual Style
 <li>
Primary Colors:

- **Deep Charcoal:**  Creates a modern and sleek background.
</li>

<li>
Accent Colors:

- **Soft White:** Ensures readability and provides contrast against darker backgrounds.
- **Muted Gray:** Used for subtle UI elements and text for a balanced look.

</li>

<li>
Visual Style:

- **Modern and Minimalist:** Emphasizes a clean, streamlined layout with a focus on functionality.
- **Bold Typography:** Uses large, clear fonts for easy navigation and readability.
- **Intuitive Navigation:** Simple and accessible design that enhances user experience through clear pathways and calls to action.
</li>   

## Entity Relational Database (ERD)
Key Entitites: 

1. **User**
   - `user_id` (Primary Key)
   - `name`
   - `email`
   - `password`
   - `date_joined`

2. **Upload Post**
- `name`
- `category`
- `location`
- `location`
- `description`
- `ownerID`

3. **Delete Post**
- `id`

4. **Like Place**
- `place_id`
- `user_id`

5. **Unlike Place**
- `place_id`
- `user_id`

6. **Bookmark Place**
- `place_id`
- `user_id`

7. **Remove Bookmarked Place**
- `place_id`
- `user_id`

##  Dataflow

1. **User Authentication & Registration:**
   - **Authentication** is used to create new users or sign in existing ones.
   - **Dataflow:** User credentials → Firebase Auth → Secure session token.

2. **Post Submission:**
   - **User Action:** Submit new project using the submission form.
   - **Dataflow:**  
     - User inputs (text)  
     - Post and User data → API backend
3. **Liking Post**
    -Frontend → POST /api/places/{place_id}/like → Backend → Database → Realtime Update
       ↑ (like action)   ↑ (rate limiting)                               ↑ (denormalized counts)

  - **Dataflow:**
    - Verify user authentication
    - Validate post exists
    - Record interaction (like)
    - Update aggregated counts

3. **Bookmarking Post**
    -Frontend → POST /api/places/{place_id}/bookmark → Backend → Database → Realtime Update
       ↑ (like action)   ↑ (rate limiting)                               ↑ (denormalized counts)

   - **Dataflow:**
    - Verify user authentication
    - Validate post exists
    - Record interaction (like)
    - Update aggregated counts


