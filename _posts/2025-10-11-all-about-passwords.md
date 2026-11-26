---
layout: post
title: "All About Passwords"
date: 2025-10-11 12:00:00
description: Exploring password security, human behavior, password cracking techniques, and defenses against credential-based attacks.
tags: cybersecurity passwords authentication cryptography
categories: technical-research
featured: false
---

## Introduction

Passwords are the keys to our digital identities. From social media accounts to financial institutions and corporate networks, passwords remain one of the most widely used methods of authentication.

Yet, despite advancements in cybersecurity, passwords remain a significant security weakness.

A study published by Kaspersky found that 59% of the passwords in its analyzed dataset could be cracked in under an hour under the study's testing conditions.

How can passwords be so vulnerable? Why do people continue to use weak passwords, how do attackers compromise them, and what can individuals and organizations do to protect themselves?

## 1. The World's Most Common Passwords

According to a dataset analyzed by NordPass in 2024, some of the world's most commonly used passwords were remarkably simple.

| Rank | Password | Number of Times Used |
| --- | --- | ---: |
| 1 | `123456` | 3,018,050 |
| 2 | `123456789` | 1,625,135 |
| 3 | `12345678` | 884,740 |
| 4 | `password` | 692,151 |
| 5 | `qwerty123` | 642,638 |

Source: NordPass (2024).

These passwords demonstrate a common problem in cybersecurity: people frequently prioritize convenience over security.

### Why Do People Use Weak Passwords?

One reason is memorability. Oftentimes, it is difficult for people to remember different passwords for every website without using a password manager. As a result, they tend to choose simpler, more predictable passwords.

For example, a password such as `123456` is much easier to remember than a randomly generated combination of letters, numbers, and symbols.

Another reason is that people may place too much trust in modern security systems. They assume that technological advancements alone will protect their information, overlooking the importance of their own security practices.

Technology alone is not foolproof. Even sophisticated security systems rely on the human element.

## 2. How Passwords Are Stored

Before understanding password cracking, it is important to understand how passwords are stored.

Secure applications should not store passwords in plaintext. Instead, they use cryptographic hashing to transform passwords into fixed-length values known as hashes.

A hash function is designed to be a one-way function, meaning that recovering the original input from its output should be computationally difficult.

When a user attempts to log in, the system processes the submitted password and verifies it against the stored password hash.

However, if an attacker obtains a database containing password hashes, they may attempt to recover the original passwords by testing possible inputs and comparing the resulting hashes.

This is known as offline password cracking.

Modern password storage systems should also use unique salts and specialized password-hashing algorithms to make these attacks more computationally expensive.

## 3. What Is Password Cracking?

Password cracking refers to techniques used to discover or recover passwords.

Threat actors may use password cracking to gain unauthorized access to accounts, sensitive information, or computer systems.

Password cracking can involve manual guessing, automated techniques, and specialized software. These tools are commonly referred to as password crackers.

One example is John the Ripper, an open-source password auditing tool used by cybersecurity professionals to evaluate password strength in authorized environments.

As technology progresses, machine learning and artificial intelligence are also being explored as ways to improve password prediction.

### Online vs. Offline Password Attacks

Password attacks can generally be divided into two categories.

| Attack Type | Description |
| --- | --- |
| Online attacks | Attempting authentication directly against a website or application |
| Offline attacks | Attempting to recover passwords from previously obtained password hashes |

Online attacks may be restricted by account lockouts, rate limits, and security monitoring.

Offline attacks are not subject to the original application's login limits. Their effectiveness depends on password strength, the hashing algorithm, and available computing resources.

## 4. The Psychology Behind Password Attacks

### Who Do Attackers Target?

Not all accounts have the same value to an attacker.

System administrators, domain administrators, and database administrators are particularly valuable targets because their accounts may have elevated privileges and access to sensitive information.

The compromise of a privileged account can have consequences far beyond the account itself. It may expose additional systems, confidential data, and other user accounts.

This illustrates the relationship between credential security and privilege escalation.

### Why Attackers Have an Advantage

Attackers often benefit from two factors:

- Time and patience.
- Automation and increasingly sophisticated password-cracking technologies.

Defenders, on the other hand, must balance security with usability. Excessively restrictive authentication policies may prevent legitimate users from accessing their accounts.

This creates a challenge for organizations attempting to prevent credential-based attacks without disrupting normal operations.

## 5. Common Password Attacks

### 5.1 Password Guessing

Usernames are often relatively predictable. In many cases, an individual's email address also serves as their username.

Passwords can become similarly predictable when users rely on familiar words, personal information, or recognizable patterns.

Common examples of weak password patterns include:

- Sequential numbers or letters.
- Variations of the word "password."
- Birthdays and other memorable dates.
- Names of relatives or pets.
- Favorite foods, colors, or hobbies.
- Predictable substitutions of letters with numbers.

Information shared publicly on social media can further increase the risks associated with passwords based on personal information.

Password guessing may generate failed authentication events that can be detected through security monitoring.

### 5.2 Dictionary Attacks

A dictionary attack is a technique that tests candidate passwords drawn from a collection of words and commonly used passwords.

Unlike brute-force attacks, dictionary attacks focus on passwords that people are more likely to choose.

They exploit the fact that human-generated passwords frequently contain recognizable words, names, and predictable variations.

However, dictionary attacks are less effective against sufficiently long, randomly generated passwords that do not follow recognizable patterns.

### 5.3 Brute-Force Attacks

A brute-force attack systematically explores possible password combinations.

The effectiveness of brute force depends heavily on password length, the number of possible characters, and the computational resources available.

The number of possible combinations can be expressed as:

$$
N = C^L
$$

Where:

- $N$ is the total number of possible combinations.
- $C$ is the number of available characters.
- $L$ is the password length.

Assuming a hypothetical character set containing 64 possible characters, the number of combinations increases exponentially with password length.

| Password Length | Calculation | Possible Combinations |
| ---: | --- | ---: |
| 4 | 64^4 | 16,777,216 |
| 5 | 64^5 | 1,073,741,824 |
| 6 | 64^6 | 68,719,476,736 |
| 7 | 64^7 | 4,398,046,511,104 |
| 8 | 64^8 | 281,474,976,710,656 |
| 9 | 64^9 | 18,014,398,509,481,984 |
| 10 | 64^10 | 1,152,921,504,606,846,976 |

Each additional character multiplies the number of possible combinations by 64.

This demonstrates why password length is such an important factor in password security.

However, the actual time required to crack a password also depends on the hashing algorithm, available hardware, and whether the password was generated randomly.

### 5.4 Credential Stuffing

Credential stuffing is an automated attack that relies on previously compromised credentials.

Unlike brute-force and dictionary attacks, credential stuffing does not necessarily involve guessing passwords. Instead, it exploits password reuse across different websites and applications.

For example, if credentials from one website are exposed in a data breach, other accounts using the same credentials may also become vulnerable.

This demonstrates how a security breach affecting one organization can create risks for users of entirely unrelated services.

Individuals can check whether their email addresses have appeared in known data breaches using:

[Have I Been Pwned](https://haveibeenpwned.com/)

### 5.5 Password Spraying

Password spraying is a credential-based attack that involves testing a small number of commonly used passwords against multiple accounts.

It differs from conventional password guessing, which typically concentrates multiple attempts on an individual account.

Password spraying highlights the limitations of relying exclusively on per-account lockout policies.

Organizations can reduce this risk through multi-factor authentication, compromised-password screening, and monitoring authentication activity across accounts.

### Comparing Password Attacks

| Attack | Primary Weakness Exploited |
| --- | --- |
| Password guessing | Predictable personal information and patterns |
| Dictionary attack | Common words and familiar passwords |
| Brute force | Insufficient password length and randomness |
| Credential stuffing | Password reuse |
| Password spraying | Common passwords across multiple accounts |

Although these attacks differ in methodology, they all demonstrate how weaknesses in password selection and authentication systems can create security vulnerabilities.

## 6. Social Engineering and Human-Based Attacks

Not every password attack requires sophisticated technology.

Social engineering involves psychological manipulation designed to trick individuals into revealing sensitive information or making security mistakes.

Instead of attacking a cryptographic system directly, social engineering targets the person using it.

The increasing sophistication of artificial intelligence, deepfakes, and automated communications introduces additional challenges in determining whether an interaction is legitimate.

### 6.1 Phishing

Phishing involves deceptive communications that impersonate legitimate individuals or organizations.

A common example is a fraudulent email claiming that a user's password has been compromised and that immediate action is required.

These messages often create a false sense of urgency to discourage careful consideration.

Users should avoid accessing password-reset pages through suspicious links and instead navigate directly to the organization's official website.

### 6.2 Vishing

Vishing, or voice phishing, relies on deceptive phone calls rather than written messages.

Attackers may impersonate banks, technical support representatives, or other trusted organizations.

Like phishing, vishing frequently relies on urgency, fear, and trust to influence a victim's decisions.

AI-generated voices introduce another challenge by making impersonation increasingly convincing.

### 6.3 Password Reset Abuse

Password reset mechanisms are designed to help legitimate users regain access to their accounts.

However, weaknesses in identity verification can allow these mechanisms to be abused.

This illustrates why account recovery procedures must be treated as an important part of authentication security rather than simply a convenience feature.

## 7. Hash-Based Attacks

### 7.1 Rainbow Table Attacks

Rainbow tables are precomputed data structures that help recover passwords from certain types of password hashes.

They use a time-memory trade-off to reduce the storage required compared with storing every possible password and its corresponding hash.

Rainbow table attacks demonstrate why storing unsalted password hashes is insecure.

A unique salt makes identical passwords produce different stored values, reducing the usefulness of precomputed tables.

### 7.2 Pass-the-Hash Attacks

Pass-the-hash (PtH) is a technique associated with authentication protocols such as NT LAN Manager (NTLM).

Rather than recovering the original human-readable password, an attacker may abuse an obtained password hash as authentication material.

This differs from conventional password cracking because the original password does not necessarily need to be discovered.

Pass-the-hash demonstrates that protecting authentication material is just as important as protecting passwords themselves.

## 8. The Problem of Password Reuse

One of the most significant weaknesses in password security is password reuse.

A survey illustrated in my original article reported the following results:

| Password Behavior | Percentage |
| --- | ---: |
| Reuse passwords for multiple, but not all, accounts | 52% |
| Use a different password for every account | 35% |
| Reuse the same password for all accounts | 13% |

According to these figures, 65% of respondents reused passwords across at least some of their accounts.

The original article did not identify the survey's sample size or methodology, so these figures should be interpreted as illustrative rather than representative of all users.

Password reuse creates a chain reaction. Even if a user creates a strong password, reusing it across multiple services increases the consequences of a single data breach.

A strong password is not necessarily a secure password if it has already been compromised elsewhere.

## 9. What Makes a Strong Password?

In today's digital world, passwords are the keys to our personal information. Yet not all passwords provide the same level of security.

Strong password practices include:

- Prioritizing password length.
- Using randomly generated passwords or long, unpredictable passphrases.
- Avoiding sequential numbers and letters.
- Avoiding predictable words and personal information.
- Using a unique password for every account.
- Changing passwords when they are suspected or known to be compromised.

Although uppercase letters, lowercase letters, numbers, and special characters can increase the number of possible combinations, predictable substitutions do not necessarily make a password secure.

Length, randomness, and uniqueness are particularly important.

For example, a randomly generated password may be more resistant to guessing than a familiar word with predictable character substitutions.

Passwords should never be reused simply because they appear sufficiently complicated.

## 10. Password Managers

Remembering a different, sufficiently strong password for every website is difficult.

Password managers address this problem by allowing users to generate and securely store unique passwords.

### Common Features of Password Managers

| Feature | Purpose |
| --- | --- |
| Secure password generation | Generates random passwords |
| Encrypted storage | Protects stored credentials using cryptography |
| Auto-fill and auto-login | Simplifies authentication |
| Cross-platform compatibility | Provides access across different devices |
| Secure sharing | Allows controlled sharing of credentials |
| Emergency access | Provides designated recovery options |
| Multi-factor authentication | Adds another layer of vault protection |

Examples of password managers include:

- [Bitwarden](https://bitwarden.com/)
- [Keeper](https://www.keepersecurity.com/)
- [KeePass](https://keepass.info/)
- [1Password](https://1password.com/)

Password managers help users avoid choosing between convenience and security.

Instead of memorizing dozens of passwords, users can protect their password vault with a strong master password and additional authentication measures.

## 11. Defending Against Password Attacks

Password security is a shared responsibility between individuals and organizations.

### For Individuals

- Use long, unique passwords.
- Use a reputable password manager.
- Enable multi-factor authentication whenever possible.
- Avoid using publicly available personal information in passwords.
- Remain cautious of suspicious emails, phone calls, and password-reset requests.
- Change passwords that have been exposed in data breaches.

### For Organizations

- Use secure, salted password-hashing algorithms.
- Implement multi-factor authentication.
- Monitor suspicious authentication activity.
- Screen passwords against known compromised-password lists.
- Protect privileged accounts.
- Apply the principle of least privilege.
- Strengthen identity verification and account recovery procedures.
- Educate employees about social engineering.

No single security mechanism can prevent every password attack. Effective protection requires multiple layers of defense.

## 12. Key Takeaways

Passwords demonstrate an important principle in cybersecurity: security is not solely a technological problem, but also a human one.

While cryptographic algorithms and authentication systems provide technical protection, their effectiveness can be undermined by predictable passwords, password reuse, social engineering, and insecure implementation.

Studying password attacks reveals how human behavior, mathematics, cryptography, and computer systems intersect.

Understanding how passwords are compromised is therefore just as important as understanding how to create strong ones.

Ultimately, password security is not about creating the most complicated password possible. It is about designing authentication practices that remain secure while being practical enough for people to use consistently.

## References

1. [NordPass — Most Common Passwords](https://nordpass.com/most-common-passwords/)
2. [Kaspersky — Passwords That Can Be Hacked in One Hour](https://www.kaspersky.com/blog/password-can-be-hacked-in-one-hour/51469/)
3. [BeyondTrust — Password Cracking 101: Attacks and Defenses Explained](https://www.beyondtrust.com/blog/entry/password-cracking-101-attacks-defenses-explained)
4. [Okta — Password Hacking](https://www.okta.com/en-au/identity-101/password-hacker/)
5. [Have I Been Pwned](https://haveibeenpwned.com/)

### Original ZeroDayJournal Articles

- [Password — September 8, 2025](https://zerodayjournal.blogspot.com/2025/09/password.html)
- [Password Cracking for Dummies — October 11, 2025](https://zerodayjournal.blogspot.com/2025/10/password-cracking-for-dummies-59-of.html)
