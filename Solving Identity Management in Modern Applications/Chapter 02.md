# 📖 Chapter 2: The Life of an Identity

## 1. Introduction: The Identity Journey
Identity management is not merely a login screen; it is a continuous journey that starts from the moment a user is first introduced to a system until they eventually leave it. Chapter 2 dives deep into the "Lifecycle of an Identity," emphasizing that developers must look beyond simple authentication. Every identity undergoes various transitions—creation, maintenance, usage, and deletion—each requiring specific security protocols and architectural considerations. Failure to manage any stage of this lifecycle can result in security vulnerabilities, such as orphaned accounts or unauthorized data access.

## 2. Defining the Core Entities (The Actors)
Before examining the lifecycle, we must define the primary actors in the identity ecosystem. These entities interact constantly to ensure secure access.

* **The Subject:** The entity seeking access. While usually a human user, it can also be a service, a bot, or an IoT device. The Subject is the "owner" of the identity.
* **The Identity Provider (IdP):** This is the central authority or the "source of truth." It stores user credentials, validates their identity, and manages their attributes.
* **The Resource Server (RS):** This server holds the valuable data or services the Subject wants to access (e.g., a database, a file storage, or an API). It relies on the IdP to verify who the user is.
* **The Client Application:** The software (mobile app, web browser, or server-side app) that the Subject uses to request access to the Resource Server.

## 3. Detailed Stages of the Identity Lifecycle

<img width="562" height="457" alt="image" src="https://github.com/user-attachments/assets/4fd62c4b-2ac1-4388-8597-991fc03e112e" />


### A. Phase 1: Provisioning (Registration and Setup)
Provisioning is the birth of an identity. It involves gathering information about a Subject and establishing their presence in the system.
* **Identity Creation:** Collecting initial data such as name, email, and password.
* **Verification:** Depending on the application's sensitivity, this might involve email verification, phone number validation, or even government ID checks (Know Your Customer - KYC).
* **Attribute Assignment:** Assigning specific roles (e.g., Admin, Editor, Viewer) and metadata that will later define what the user can do.
* **Unique Identifiers:** The system must assign a permanent, unique identifier (like a GUID) to ensure that even if a username changes, the identity remains consistent.

### B. Phase 2: Authentication (Proving Who You Are)
This is the most visible part of the lifecycle. The goal is to verify the Subject's identity using one or more factors.
* **Single-Factor vs. Multi-Factor:** Moving beyond passwords to include "something you have" (OTP, hardware key) or "something you are" (fingerprint, face ID).
* **Adaptive Authentication:** Modern systems analyze context—such as IP address, location, and time of day—to decide if additional security checks are needed.

### C. Phase 3: Authorization (Defining What You Can Do)
After identity is confirmed, the system must decide the scope of access. 
* **Role-Based Access Control (RBAC):** Permissions assigned based on job functions.
* **Attribute-Based Access Control (ABAC):** More granular control based on user attributes, environment, and resource type.
* **Policy Enforcement:** The mechanism that actually blocks or allows an action based on the authorization rules.

### D. Phase 4: Maintenance and Self-Service
Identities are dynamic. Users need tools to manage their own data without administrator intervention.
* **Profile Management:** Updating personal information or changing security settings.
* **Credential Recovery:** A secure workflow for resetting lost passwords or recovering accounts after losing an MFA device. This is a critical security area, as hackers often target recovery flows.

### E. Phase 5: Sessions and SSO
To provide a smooth experience, systems use sessions and Single Sign-On.
* **Session Management:** Balancing security and convenience by determining how long a user stays logged in before needing to re-authenticate.
* **Single Sign-On (SSO):** Allowing a user to log in once to a trusted IdP and gain access to multiple independent resource servers.

### F. Phase 6: Deprovisioning (The End of the Identity)
This is often the most overlooked stage but is vital for security.
* **Termination:** When a user leaves an organization or closes an account, access must be revoked immediately across all systems.
* **Orphaned Accounts:** Accounts that remain active after a user has left. These are major targets for attackers because they are often unmonitored.
* **Data Retention and Deletion:** Complying with privacy laws like GDPR to ensure user data is removed or anonymized upon request.

## 4. The Architecture of Trust
The entire lifecycle depends on a "Trust Relationship" between the Identity Provider and the Resource Server. The Resource Server doesn't need to know the user's password; it only needs to trust that when the IdP says "This is User A," it is telling the truth. This trust is established through digital signatures and cryptographic tokens.

## 5. Security vs. Friction
A recurring theme in this chapter is the trade-off between security and user experience (UX). Every additional security step (like MFA) adds "friction." The goal of a modern identity system is to provide a "frictionless" experience for legitimate users while maintaining a high barrier for attackers.

## Summary
This chapter has introduced the concept of an account and an associated identity and the most typical events that occur during their existence, from provisioning and authorization to authentication and access policy enforcement, all the way to deprovisioning. 
In the next chapters, we’ll dive into more detail for each event, starting with a summarized history of approaches to identity management.

## Key Points
* Provisioning creates an account and associated identity.
* Authentication validates a user is entitled to use an account.
* Authorization specifies the privileges granted for an account.
* Access policy enforcement checks that requests are within the privileges granted by authorization.
* A session and session limit are used to govern how long a user can remain active without reauthenticating.
* Single sign-on allows a user to log in once and then access additional protected resources without reentering credentials.
---

# 📑 Vocabulary List (30 Words)

| No | Word | Korean Meaning |
| :--- | :--- | :--- |
| 1 | **Subject** | 주체 (인증의 대상) |
| 2 | **Identity Provider (IdP)** | 아이덴티티 제공자 |
| 3 | **Resource Server (RS)** | 리소스 서버 |
| 4 | **Provisioning** | 프로비저닝 (계정 생성 및 설정) |
| 5 | **Deprovisioning** | 디프로비저닝 (계정 회수 및 삭제) |
| 6 | **Authentication** | 인증 (신원 확인) |
| 7 | **Authorization** | 권한 부여 (접근 허가) |
| 8 | **Lifecycle** | 생명주기 |
| 9 | **Credential** | 자격 증명 (비밀번호 등) |
| 10 | **Attribute** | 속성 (이름, 역할 등) |
| 11 | **Identifier** | 식별자 (고유 ID) |
| 12 | **Entity** | 엔티티 (개체) |
| 13 | **Single Sign-On (SSO)** | 싱글 사인온 |
| 14 | **Multi-factor (MFA)** | 다요소 인증 |
| 15 | **Friction** | 마찰 (사용자 불편 요소) |
| 16 | **Frictionless** | 마찰 없는 (매끄러운 UX) |
| 17 | **Session** | 세션 (연결 유지 기간) |
| 18 | **Token** | 토큰 (인증 증표) |
| 19 | **Trust Relationship** | 신뢰 관계 |
| 20 | **Policy Enforcement** | 정책 실행 |
| 21 | **Self-Service** | 셀프 서비스 (사용자 직접 관리) |
| 22 | **Recovery** | 복구 |
| 23 | **Orphaned Account** | 고아 계정 (방치된 계정) |
| 24 | **Revocation** | 철회/취소 |
| 25 | **Granular** | 세밀한/알갱이의 |
| 26 | **Metadata** | 메타데이터 |
| 27 | **Compliance** | 준수 (법규 등) |
| 28 | **Scalability** | 확장성 |
| 29 | **Architecture** | 아키텍처 (구조) |
| 30 | **Vulnerability** | 취약점 |

---
*Source: Solving Identity Management in Modern Applications, Chapter 2*
