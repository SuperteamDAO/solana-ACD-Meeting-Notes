# Solana Core-Dev sync #1

## Introduction
- Jacob Creech, Richie Patel

Explaining the agenda of the meeting.

⏰ 00:00 - 02:30

The purpose of this call is for developers on the Solana protocol to stay informed about developments that are happening within the protocol and to have a process for proposing changes that they would like to see implemented. The call is intended to be a forum for developers to collaborate and communicate with each other, and to ensure that everyone is aligned on the direction of the Solana protocol.

Richie suggests that an online forum would be a useful platform for discussing changes that affect everyone within the Solana community, particularly protocol-breaking changes that are made by Solana labs and Judo finance.

Jacob mentions that they will also discuss SIMDs (Solana Improvement Document) and that attendees are welcome to bring up any other topics that they would like to discuss. He also mentions that in future calls, they may call for an agenda and ask attendees to propose topics that they would like to see on the agenda. This will allow attendees to have a say in the direction of the conversation and ensure that their concerns and ideas are heard.

## Read and Write access on Solana Protocol
- Dan Albert

Discussing how can we put out more visibility to the broader community.

⏰ 02:40 - 04:52

- There has been a lot of demand from the community for access to information and the ability to propose changes to the Solana protocol.
- Many teams, both core, and non-core developers want better visibility into what changes are coming and how they will impact them.
- The core developer community can do a better job of communicating and providing visibility to the broader community.
- There is a need to figure out how to make contributions and engage with the community, such as through informal proposals on Discord or other forums, and to establish an approval process for these contributions.
- There is a need to determine whether anyone should be responsible for approving contributions, and to consider whether anyone should be able to build from source and run a client with their own changes.
- There is a need to gather feedback on specific proposals and code changes.

## Challenges in making public repos and their possible solutions.
- Kevin Bowers

An overview on what are the challenges involved in making Solana Repo public for community contributions and how we plan to tackle them.

⏰ 06:08 - 09:46

- One of the goals of the Solana team is to create specs for the existing protocol based on the current code.
- These specs are necessary for formal verification of the protocol.
- The Solana Foundation has set up repos for this purpose, and there have been comments and concerns from the community about access and direction.
- The team has considered the best model for engaging with the community and developing the protocol.
- They were concerned about the potential challenges of working with different organizations, cultures, development styles, and languages in the same repo.
- They have experience with developing at boundaries between repos and creating interfaces in other projects.
- They plan to iterate independently in their own repo, using the specs to define boundaries and componentize the existing validator.
- This will allow them to swap out different parts of the validator as they go and avoid tight integration between organizations.
- This approach will involve working at process boundaries to minimize friction.
- The team has not prepared specific remarks or plans for this discussion.

## Taking inspiration from the EIP process for SIMD
- Richie Patel, Dan Albert, Jacob Creech, Anatoly Yakovenko

⏰ 10:00 - 15:07

- Richie suggests that the group can take inspiration from the Ethereum process, which has proven to be effective at scale and has similarities to the process they are considering for proposing and implementing changes to the Solana protocol through SIMD. He mentions the importance of checking in an EIP or SIMD, as well as having a proof of concept in one's own repo and thinking ahead about how other teams might implement the changes.
- Dan believes that the bar for getting a SIMD merged should be high and that it should be the final step in a more formal process of debate, testing, and prototyping. They also mention the importance of getting initial social consensus from the validator and developer communities and having a proven concept before moving to a SIMD.
- Richie suggests that the process for implementing non-trivial changes to specifications should involve checking in a proof of concept to a repository and thinking about how another team might implement it, similar to the process used by the Ethereum community. Dan agrees with this proposal and suggests that the bar for getting a SIMD merged should be high, with initial social consensus from the developer community and at least one team willing to implement it.
- Dan also suggests that proposals should not be jumped to SIMD for random new ideas, but rather should be discussed in Discord or GitHub issues to suss out interest and feasibility. Richie points out that the Ethereum community also checks in a lot of EIPs that are never actually deployed on mainnet, but suggests that having an acceptable standard can be helpful when implementing an idea. Dan expresses concern about having a repository filled with unimplemented proposals and suggests that there should be a filtering mechanism in place.
- Anatoly adds that it is important for the specs that are checked in to have a path to implementation within six months to avoid wasting time on ideas that may no longer be valid.
- Jacob mentions that in the Ethereum community, there is a process for proposals for changes to the network. This process includes a draft phase where consensus is sought on whether the proposal should move forward and an implementation phase where the details of how the proposal will be implemented and activated on the network are worked out. Kevin Galler asks if there is a mechanism for marking the status of these proposals, and Jacob explains that there is a process outlined in the first SIMD that includes draft, accepted, and implementation phases, and outlines the process for feature activation and ownership of implementation by different clients.

## Merging the code changes - Access and Authorization.
- Richie Patel, Jacob Creech, Dan Albert, Anatoly Yakovenko 

⏰ 15:11 - 18:46

- Richie is discussing the process of merging code changes into a codebase, specifically in the context of the Solana project. Richie raises the question of who has the authority to press the "merge button" to integrate the changes, and mentions that Solana Labs and the Solana Foundation currently have this authority.
- Jacob mentions that changes should only be made if there is no obvious disagreement and there is agreement from the majority of core contributors. He also suggests that an access policy, similar to the one used by Mozilla, should be considered and will be used to create a list of people who have the ability to make changes to the repository. This process involves both social consensus and technical consensus, and the ability to make changes can be taken away if someone abuses their power.
- Dan mentions about the process for submitting and merging changes or pull requests (PRs) to a repository related to the SIMDs. Dan mentions that the quality of PRs may have been mixed and wonders if there is a written or informal process for receiving and merging changes from community members or others, and asks Anatoly how the Labs team views these submissions.
- Anatoly suggests that if a change or addition to the system involves a feature activation, it should be accompanied by a proposal. The reason for this is that the feature activation indicates that there is something significant or potentially disruptive being implemented, and it needs to be communicated to all relevant parties and discussed through the proposal process.

## Take on validator changes, API Hooks and plans of Fire dancer team.
- Buffalu Jito, Anatoly Yakovenko, Dan Albert

⏰ 18:52 - 21:01

- Buffalu asks Anatoly his opinion about the validator changes made recently, he mentions they may not be related to consensus but they are significant changes.
- Anatoly suggests creating a proposal for API hooks that all conforming clients should implement, and that the fire dancer team and the Lab’s team can confirm to this standard. Anatoly mentions the need to load a dynamic shared object instead of downloading a separate client.
- Dan mentions that even fire dancer team had same plans of basically having kind of a spec or design out of the interfaces that aren’t necessarily a protocol defining but it’s more of like an implementation.
- Kevin agrees that those are definitely fresh on their minds as close to getting the last bits of plumbing put together at their end. There are different ways to approach from a process standpoint or a repo standpoint but the intent is to take the existing validator at Solana and do all the plumbing that’s needed on the interface side with the component and then forward it to the next team and figure out a way.

## Concerns with internal validator API repo and how the process will look like once the SIMD is accepted.
- Richie Patel, Dan Albert, Jacob Creech

⏰ 21:30 - 23:34

- Richie recollects a process where as a part of three repos the team created for inter client and local apis, along with these specs and SIMDs there were also a validated apis that Ripple and Solana Foundation created.
- Originally that was the plan to have all the C structure definitions and so on post, but he raises a concern that it might soon get complicated if that needs to be compatible with three different CI processes and keep them in sync.
- Dan agrees to Richie and mentions that there has been no significant activity in the internal validator API repo and he is happy to remove it as they have scrapped the idea a while ago and it’s not a protocol definition, but an implementation for convenience between multiple teams.
- Jacob asks about the process for updating specifications when a SIMD proposal is accepted. If it is necessary to wait until the proposal has been implemented across different clients before updating the specs, or if the specs should be changed in accordance with upgrades to the network.
- Richie is discuss the relationship between proposed changes and specifications, stating that the specs are the authoritative sources of what the protocol is. He mentions that it might be technically wrong to merge proposed changes into the specs before they are activated on the mainnode, but express uncertainty about whether they want to "split hairs" on this issue. The speaker suggests that it might be a good idea to merge proposed changes into the specs repo when a feature is about to be activated.