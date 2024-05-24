# Voting Management System in C

The Voting Management System is a console-based application designed to manage the voting process efficiently and transparently. Implemented in the C programming language, this system allows for voter registration, candidate addition, vote casting, and result display. It is structured to be simple and intuitive, making it easy to understand and use.

# Features

1. **User Registration**:
   - Allows users to register as voters by providing their names and unique IDs.
   - Each voter is stored in an array of `Voter` structures.
   - Voters can only register if the registration limit (MAX_VOTERS) is not reached.

2. **Candidate Addition**:
   - Enables the addition of candidates to the election.
   - Each candidate's name is stored in an array of `Candidate` structures.
   - Candidates can only be added if the candidate limit (MAX_CANDIDATES) is not reached.

3. **Vote Casting**:
   - Registered voters can cast their vote for any of the candidates.
   - The system checks if the voter has already voted to prevent multiple votes.
   - Votes are tallied in the `votes` field of the corresponding `Candidate` structure.

4. **Result Display**:
   - Displays the total number of votes each candidate has received.
   - Provides a clear view of the election outcome.

# Structures

- **Voter**:
  ```c
  typedef struct {
      char name[50];
      int id;
      int hasVoted;
  } Voter;
  ```
  - `name`: Stores the name of the voter.
  - `id`: Unique identifier for the voter.
  - `hasVoted`: Flag indicating whether the voter has cast their vote.

- **Candidate**:
  ```c
  typedef struct {
      char name[50];
      int votes;
  } Candidate;
  ```
  - `name`: Stores the name of the candidate.
  - `votes`: Counter for the number of votes received by the candidate.

#### Functions

- **registerVoter()**:
  - Registers a new voter by taking their name and ID.
  - Checks if the voter registration limit has been reached.

- **addCandidate()**:
  - Adds a new candidate by taking their name.
  - Checks if the candidate limit has been reached.

- **castVote()**:
  - Allows a registered voter to cast a vote for a candidate.
  - Ensures that the voter has not already voted and that the candidate number is valid.

- **showResults()**:
  - Displays the total votes each candidate has received.

- **findVoterById(int id)**:
  - Searches for a voter by their ID and returns their index in the voters array.
  - Returns -1 if the voter is not found.

- **initializeCandidates()**:
  - Optionally initializes the system with some default candidates.

#### Usage

1. **Compile the Program**:
   - Use a C compiler like `gcc` to compile the program:
     ```sh
     gcc voting_management_system.c -o voting_management_system
     ```

2. **Run the Program**:
   - Execute the compiled program:
     ```sh
     ./voting_management_system
     ```

3. **Menu Options**:
   - **Register Voter**: Allows you to register new voters.
   - **Add Candidate**: Allows you to add new candidates.
   - **Cast Vote**: Enables registered voters to vote for candidates.
   - **Show Results**: Displays the election results.
   - **Exit**: Terminates the program.

This voting management system serves as a basic framework and can be extended with additional features like input validation, secure data handling, and a graphical user interface for enhanced usability.
