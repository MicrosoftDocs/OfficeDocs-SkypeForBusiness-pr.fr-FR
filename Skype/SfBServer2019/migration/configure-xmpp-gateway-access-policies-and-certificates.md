---
title: Configuration des certificats et des stratégies d’accès de passerelle XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'La fédération XMPP définit un déploiement externe basé sur le protocole XMPP (eXtensible Messaging and Presence Protocol). Une configuration XMPP permet aux utilisateurs d’accéder aux utilisateurs de domaine XMPP en :'
ms.openlocfilehash: f94cd3bc0a769165f6ffe8ecabea8b7f48a1ff07
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753934"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="b72e2-104">Configuration des certificats et des stratégies d’accès de passerelle XMPP</span><span class="sxs-lookup"><span data-stu-id="b72e2-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="b72e2-105">La fédération XMPP définit un déploiement externe basé sur le protocole XMPP (eXtensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="b72e2-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="b72e2-106">Une configuration XMPP permet aux utilisateurs d’accéder aux utilisateurs de domaine XMPP en :</span><span class="sxs-lookup"><span data-stu-id="b72e2-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="b72e2-107">Messagerie instantanée et présence : personne à personne uniquement</span><span class="sxs-lookup"><span data-stu-id="b72e2-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="b72e2-108">Création de contacts fédérés XMPP dans le client Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="b72e2-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="b72e2-109">Lorsque vous configurez des stratégies pour la prise en charge des partenaires fédérés XMPP, les stratégies s’appliquent aux utilisateurs de domaines fédérés XMPP, mais pas aux utilisateurs de fournisseurs de services de messagerie instantanée SIP (Session Initiation Protocol) ou aux domaines fédérés SIP.</span><span class="sxs-lookup"><span data-stu-id="b72e2-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="b72e2-110">Vous configurez un partenaire fédéré XMPP pour chaque domaine fédéré XMPP avec qui vous souhaitez permettre à vos utilisateurs d’ajouter des contacts et de communiquer.</span><span class="sxs-lookup"><span data-stu-id="b72e2-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="b72e2-111">Une fois les stratégies en place, vous devez configurer les certificats de passerelle XMPP.</span><span class="sxs-lookup"><span data-stu-id="b72e2-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b72e2-112">La fonctionnalité XMPP est dépréciée dans Skype Entreprise Server 2019, mais peut être poursuivie dans un serveur hérité en coexistence avec Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b72e2-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="b72e2-113">Assurez-vous que vous avez déjà déployé la passerelle XMPP du serveur hérité (Skype Entreprise Server 2015 / Lync Server 2013) et configuré les stratégies d’accès pour permettre aux utilisateurs d’utiliser la passerelle XMPP héritée.</span><span class="sxs-lookup"><span data-stu-id="b72e2-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="b72e2-114">Pour plus d’informations, [voir Migration de la fédération XMPP.](migrating-xmpp-federation.md)</span><span class="sxs-lookup"><span data-stu-id="b72e2-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="b72e2-115">Configurer une stratégie d’accès externe pour activer les utilisateurs pour la passerelle XMPP héritée</span><span class="sxs-lookup"><span data-stu-id="b72e2-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="b72e2-116">Ouvrez le Panneau de contrôle Skype Entreprise Server hérité.</span><span class="sxs-lookup"><span data-stu-id="b72e2-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="b72e2-117">Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="b72e2-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="b72e2-118">Cliquez sur **Nouvelle**, puis sur **Stratégie utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="b72e2-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="b72e2-119">Entrez un nom pour la stratégie utilisateur d’accès externe.</span><span class="sxs-lookup"><span data-stu-id="b72e2-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="b72e2-120">Fournissez une description pour la stratégie utilisateur d’accès externe.</span><span class="sxs-lookup"><span data-stu-id="b72e2-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="b72e2-121">Sélectionnez **Activer les communications avec les utilisateurs fédérés**.</span><span class="sxs-lookup"><span data-stu-id="b72e2-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="b72e2-122">Sélectionnez **Activer les communications avec les utilisateurs fédérés XMPP**.</span><span class="sxs-lookup"><span data-stu-id="b72e2-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="b72e2-123">Cliquez sur **Valider** pour enregistrer les modifications apportées à la stratégie de site ou utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b72e2-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

