---
title: Infrastructure de sécurité pour Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent l’infrastructure de sécurité de Skype pour Business Server. Il est essentiel pour les décisions adéquates sur la sécurisation de votre Skype particulier pour le déploiement de serveur d’entreprise de comprendre comment ces éléments fonctionnent ensemble.
ms.openlocfilehash: 7c678e1f005178b569f8e4136d40fd911483a3d5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879881"
---
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="4424e-104">Infrastructure de sécurité pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="4424e-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="4424e-105">Cette section fournit une vue d’ensemble des éléments fondamentaux qui constituent l’infrastructure de sécurité de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="4424e-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="4424e-106">Il est essentiel pour les décisions adéquates sur la sécurisation de votre Skype particulier pour le déploiement de serveur d’entreprise de comprendre comment ces éléments fonctionnent ensemble.</span><span class="sxs-lookup"><span data-stu-id="4424e-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="4424e-107">Ces éléments sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="4424e-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="4424e-108">Services de domaine Active Directory (AD DS) fournit un référentiel centralisé approuvé unique pour les comptes d’utilisateurs et les ressources réseau.</span><span class="sxs-lookup"><span data-stu-id="4424e-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="4424e-109">RBAC (Contrôle d’accès basé sur un rôle) vous permet de déléguer les tâches d’administration tout en maintenant des normes élevées en matière de sécurité.</span><span class="sxs-lookup"><span data-stu-id="4424e-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="4424e-110">L’infrastructure à clé publique (PKI, Public Key Infrastructure) utilise des certificats émis par des autorités de certification approuvées afin d’authentifier les serveurs et de garantir l’intégrité des données.</span><span class="sxs-lookup"><span data-stu-id="4424e-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="4424e-p103">Le protocole de transport TLS (Transport Layer Security), HTTPS sur SSL (HTTPS) et MTLS (Mutual TLS) permettent l’authentification des points de terminaison et le chiffrement des messages instantanés. Les flux multimédias point à point sont chiffrés à l’aide du protocole SRTP (protocole de transport sécurisé en temps réel).</span><span class="sxs-lookup"><span data-stu-id="4424e-p103">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption. Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="4424e-113">Protocoles standard d’authentification des utilisateurs, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="4424e-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="4424e-114">Windows PowerShell propose des fonctionnalités de sécurité qui sont activées par défaut afin que les utilisateurs ne peuvent pas facilement ou sans le savoir exécuter les scripts.</span><span class="sxs-lookup"><span data-stu-id="4424e-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="4424e-115">Ces éléments fondamentaux de la sécurité fonctionnent ensemble pour définir les utilisateurs approuvés, serveurs, connexions et opérations pour garantir sécurisées pour Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="4424e-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="4424e-116">Contenu de cette section</span><span class="sxs-lookup"><span data-stu-id="4424e-116">In this section</span></span>

<span data-ttu-id="4424e-117">Les rubriques de cette section décrivent comment chacun de ces éléments fondamentaux pour améliorer la sécurité de votre Skype pour l’infrastructure de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="4424e-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="4424e-118">Services de domaine Active Directory pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="4424e-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="4424e-119">Contrôle d’accès basé sur un rôle (RBAC) pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="4424e-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="4424e-120">Infrastructure à clé publique pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="4424e-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="4424e-121">TLS et MTLS pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="4424e-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="4424e-122">Chiffrement pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="4424e-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="4424e-123">Authentification utilisateur et client pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="4424e-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="4424e-124">Windows PowerShell et Skype pour les outils de gestion de serveur d’entreprise</span><span class="sxs-lookup"><span data-stu-id="4424e-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

