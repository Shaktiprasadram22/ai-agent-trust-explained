# AI Agent Trust, Explained

A simple guide to why websites need to recognize AI assistants, understand whom they represent, and know who is responsible for their actions.

Based on **“Agents aren’t humans (but they kinda are)”** by **Bryan Becker**, published on the **Cloudflare Blog on November 5, 2026**, as supplied by the repository owner.

📖 [Read the original article text](articles/agents-arent-humans.md)

## The problem in one minute

Imagine you ask an AI assistant to buy a pair of shoes.

When you shop directly, the store can use your account, device, and purchase history to recognize you. When a cloud-hosted assistant shops for you, the store may see the assistant’s infrastructure and lose some of those signals.

The same AI service can also act for thousands of other people. That makes a few things harder:

- **Stopping abuse:** Blocking one shared service can block innocent users too.
- **Proving authorization:** The store needs evidence that you approved a purchase.
- **Handling mistakes:** Someone must deal with duplicate orders, refunds, and disputes.
- **Managing resources:** Assistants can check prices or search far more frequently than people.

A CAPTCHA only checks whether a human can complete a challenge. It does not establish which user the assistant represents or what that user authorized.

## The proposed solution

Give websites and assistants a shared way to exchange trustworthy information and rules.

| Part | In simple words | Example |
| --- | --- | --- |
| Agent identity | Prove which AI service is making the request. | The service digitally signs a request. |
| User connection | Connect actions to the relevant user when needed. | The assistant uses authorization tied to your store account. |
| Relevant claims | Prove only the facts needed for an action. | Provide trusted proof of an age requirement. |
| Website policies | Tell assistants what actions are allowed and under what conditions. | Publish access requirements and request limits. |
| Reputation and accountability | Assess reliability and establish who answers for actions. | Keep authorization records and agree on how errors and disputes are handled. |

Different actions need different information. Reading a public page may require no identity. Accessing a bank account needs stronger verification. This does not require giving every website your real name or a universal identifier.

## A simple shopping example

1. You authorize your assistant to shop within an agreed budget.
2. The assistant proves which service it belongs to.
3. The store connects the request to your account and checks the required permissions and claims.
4. The assistant follows the store’s access and transaction rules.
5. The purchase is recorded with evidence of authorization.
6. If something goes wrong, the parties use those records and their agreements to handle it.

This is an illustration of the proposed approach, not a finished checkout protocol. A signed request or an OAuth token alone does not prove approval of every purchase or decide liability.

## What the names mean

| Name in the article | What it contributes |
| --- | --- |
| **Web Bot Auth (WBA)** | Signed requests that identify an agent service and, implicitly, its operator. |
| **OAuth** | Account-linked authorization that can help connect an assistant’s access to a user. |
| **Privacy Pass / MOLE** | Privacy-preserving approaches to trust and access control; the article describes MOLE as an emerging approach to rate limiting. |
| **Site agent access policy** | Machine-readable rules describing what assistants may do. The broader standard described in the article is still needed. |
| **Trusted Agent Delegation (TAD)** | A coalition intended to help participants define problems and develop interoperable solutions through standards work. |

## What is available and what is still a proposal?

The supplied article reports that Cloudflare has introduced agent traffic visibility, access policies, and account-level abuse controls, with Account Abuse Protection in early access.

The broader system is still developing. Chained intermediaries, trustworthy user claims, interoperable action policies, and accountability across services are not all solved by one protocol or product.

The article primarily concerns **cloud-hosted assistants**. Local and on-device agents have different trust challenges and are outside its initial focus.

## Repository contents

- [`README.md`](README.md): this plain-language explanation.
- [`articles/agents-arent-humans.md`](articles/agents-arent-humans.md): the supplied article, credited to its author and publisher, with webpage navigation removed.

This is a documentation-only repository. No installation or build is needed, and there is no CI/CD pipeline.
