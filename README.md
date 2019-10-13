# GVSU Open Source Network

## Proposal

### Introduction
If you're a computer science student and you want to become a better programmer or you're looking for a job or internship, one of the most common pieces of advices is that you should have side projects or contribute to open-source. But the problem is contributing to open-source projects can be intimidating when you're first starting out.

Our solution to this is the GVSU Open Source Network, a small networking site where students, alumni, and professors can link to their open-source projects and include how they can contribute. While there are sites like GitHub that have many open-source projects already, this solution allows for developers in the GVSU community to meet in real life. This also helps current GVSU CIS students network and develop OSS along-side GVSU alum currently in the workforce. If the GVSU Open Source Network becomes accessible from the cis.gvsu.edu homepage, then this would act as a good way for GVSU CIS to advertise the success of the program.

### Development Stack
This site would be developed using React, React Hooks, Redux, Firebase, TypeScript, and styled-components. The database for this project will be created using Firebase Cloud Firestore.

### Features
- Ability to create and view projects
- Ability to customize profile
- Ability to search and filter projects
- Colored indicator show online users
- Notifications for comments
- Admin account to approve and remove projects
- Admin account to ban users
- Extra: GitHub API integration

### Rough Table Design
```typescript
// User
{
    id: string,
    isOnline: boolean,
    name: string,
    email: string,
    role: "default" | "admin",
    userType: "student" | "professor" | "alumnus",
    about: string,
    ownedProjects: Project[],
    contributingToProjects: Projects[],
    likedProjects: Project[]
}
// Project
{
    name: string,
    owner: User,
    description: string,
    contributeGuide: string,
    comments: Comment[],
    contributors: User[],
    events: Event[],
    tags: Tag[],
    likes: number
}
// Tag
{
    name: string
}
// Event
{
    name: string,
    dateTime: Date,
    description: string,
    owner: User,
    usersAttending: User[]
    comments: Comment[]
}
// Comment
{
    comment: string,
    responses: Comment[]
}
```