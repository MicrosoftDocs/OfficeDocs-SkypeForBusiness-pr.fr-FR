---
title: Configuration des certificats et des stratégies d’accès de passerelle XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'La Fédération XMPP définit un déploiement externe en fonction du protocole XMPP (eXtensible Messaging and Presence Protocol). Une configuration XMPP permet aux utilisateurs d’accéder aux utilisateurs de domaine XMPP en procédant comme suit:'
ms.openlocfilehash: c5231016729cd40619bbcfe48ebfcf59eff9182a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275572"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="9ffec-104">Configuration des certificats et des stratégies d’accès de passerelle XMPP</span><span class="sxs-lookup"><span data-stu-id="9ffec-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="9ffec-105">La Fédération XMPP définit un déploiement externe en fonction du protocole XMPP (eXtensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="9ffec-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="9ffec-106">Une configuration XMPP permet aux utilisateurs d’accéder aux utilisateurs de domaine XMPP en procédant comme suit:</span><span class="sxs-lookup"><span data-stu-id="9ffec-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="9ffec-107">Messagerie instantanée et présence-personne uniquement</span><span class="sxs-lookup"><span data-stu-id="9ffec-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="9ffec-108">Création de contacts fédérés de XMPP dans le client Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="9ffec-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="9ffec-109">Lorsque vous configurez des stratégies pour la prise en charge des partenaires fédérés XMPP, les stratégies s’appliquent aux utilisateurs des domaines fédérés de XMPP, mais pas aux utilisateurs des fournisseurs de services de messagerie instantanée SIP (Session Initiation Protocol) ou de domaines fédérés SIP.</span><span class="sxs-lookup"><span data-stu-id="9ffec-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="9ffec-110">Vous configurez un partenaire fédéré de XMPP pour chaque domaine fédéré XMPP que vous voulez autoriser vos utilisateurs à ajouter des contacts et à communiquer avec eux.</span><span class="sxs-lookup"><span data-stu-id="9ffec-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="9ffec-111">Une fois les stratégies en place, vous devez configurer les certificats de passerelle XMPP.</span><span class="sxs-lookup"><span data-stu-id="9ffec-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9ffec-112">La fonctionnalité XMPP est déconseillée dans Skype entreprise Server 2019, mais peut être poursuivie dans un serveur hérité pour coexistence avec Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9ffec-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="9ffec-113">Assurez-vous d’avoir déjà déployé le serveur hérité (Skype entreprise Server 2015/Lync Server 2013) et configuré les stratégies d’accès pour permettre aux utilisateurs de la passerelle XMPP héritée.</span><span class="sxs-lookup"><span data-stu-id="9ffec-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="9ffec-114">Pour plus d’informations, consultez Migration de la [Fédération XMPP](migrating-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="9ffec-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="9ffec-115">Configurer une stratégie d’accès externe pour permettre aux utilisateurs de l’ancienne passerelle XMPP</span><span class="sxs-lookup"><span data-stu-id="9ffec-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="9ffec-116">Ouvrez l’ancien panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9ffec-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="9ffec-117">Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="9ffec-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="9ffec-118">Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="9ffec-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="9ffec-119">Entrez le nom de la stratégie de l’utilisateur pour l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="9ffec-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="9ffec-120">Entrez une description pour la stratégie utilisateur d’accès externe.</span><span class="sxs-lookup"><span data-stu-id="9ffec-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="9ffec-121">Sélectionnez **activer les communications avec les utilisateurs fédérés**.</span><span class="sxs-lookup"><span data-stu-id="9ffec-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="9ffec-122">Sélectionnez **activer les communications avec les utilisateurs fédérés de XMPP**.</span><span class="sxs-lookup"><span data-stu-id="9ffec-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="9ffec-123">Cliquez sur **valider** pour enregistrer les modifications apportées à la stratégie de site ou d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9ffec-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

