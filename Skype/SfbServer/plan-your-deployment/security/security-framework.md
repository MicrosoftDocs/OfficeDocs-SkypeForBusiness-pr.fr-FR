---
title: Infrastructure de sécurité pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent l’infrastructure de sécurité pour Skype Entreprise Server. Il est essentiel de comprendre comment ces éléments fonctionnent ensemble pour prendre des décisions éclairées sur la sécurisation de votre déploiement Skype Entreprise Server particulier.
ms.openlocfilehash: 94d2ffac30e029ab6631557a69d6da3ec108657f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832094"
---
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="12ed7-104">Infrastructure de sécurité pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="12ed7-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="12ed7-105">Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent l’infrastructure de sécurité pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="12ed7-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="12ed7-106">Il est essentiel de comprendre comment ces éléments fonctionnent ensemble pour prendre des décisions éclairées sur la sécurisation de votre déploiement Skype Entreprise Server particulier.</span><span class="sxs-lookup"><span data-stu-id="12ed7-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="12ed7-107">Ces éléments sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="12ed7-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="12ed7-108">Les services de domaine Active Directory offrent un référentiel centralisé, unique et fiable aux comptes d’utilisateurs et aux ressources réseau.</span><span class="sxs-lookup"><span data-stu-id="12ed7-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="12ed7-109">Role-Based contrôle d’accès (RBAC) vous permet de déléguer des tâches administratives tout en maintenant des normes de sécurité élevées.</span><span class="sxs-lookup"><span data-stu-id="12ed7-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="12ed7-110">L’infrastructure à clé publique (PKI) utilise des certificats émis par des autorités de certification (CA) pour authentifier les serveurs et garantir l’intégrité des données.</span><span class="sxs-lookup"><span data-stu-id="12ed7-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="12ed7-p103">Les protocoles TLS (Transport Layer Security), HTTPS sur SSL (HTTPS) et Mutual TLS (MTLS) permettent l’authentification des systèmes d’extrémité et le chiffrement des communications par messagerie instantanée. Les flux audio, vidéo et de partage d’application point à point sont chiffrés à l’aide du protocole SRTP (Secure Real Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="12ed7-p103">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="12ed7-113">Des protocoles standard sont utilisés pour l’authentification des utilisateurs, lorsque cela est possible.</span><span class="sxs-lookup"><span data-stu-id="12ed7-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="12ed7-114">Windows PowerShell propose des fonctionnalités de sécurité activées par défaut afin que les utilisateurs ne puissent pas exécuter des scripts facilement ou sans le savoir.</span><span class="sxs-lookup"><span data-stu-id="12ed7-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="12ed7-115">Ces éléments de sécurité fondamentaux fonctionnent ensemble pour définir des utilisateurs, des serveurs, des connexions et des opérations de confiance afin de garantir une base sécurisée pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="12ed7-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="12ed7-116">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="12ed7-116">In this section</span></span>

<span data-ttu-id="12ed7-117">Les rubriques de cette section décrivent comment chacun de ces éléments fondamentaux fonctionne pour améliorer la sécurité de votre infrastructure Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="12ed7-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="12ed7-118">Services de domaine Active Directory pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="12ed7-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="12ed7-119">Contrôle d’accès basé sur un rôle (RBAC) pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="12ed7-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="12ed7-120">Infrastructure à clé publique pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="12ed7-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="12ed7-121">TLS et MTLS pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="12ed7-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="12ed7-122">Chiffrement pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="12ed7-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="12ed7-123">Authentification des utilisateurs et des clients pour Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="12ed7-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="12ed7-124">Windows PowerShell de gestion de Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="12ed7-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

