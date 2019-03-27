---
title: Configuration des certificats et des stratégies d’accès de passerelle XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'La fédération XMPP définit un déploiement externe en fonction des eXtensible Messaging et présence protocole XMPP (). Une configuration XMPP permet aux utilisateurs d’accéder à des utilisateurs de domaine XMPP par :'
ms.openlocfilehash: 65ef8904660eaa75ddd10238a6561ea91b9f7278
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889972"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="8e99d-104">Configuration des certificats et des stratégies d’accès de passerelle XMPP</span><span class="sxs-lookup"><span data-stu-id="8e99d-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="8e99d-105">La fédération XMPP définit un déploiement externe en fonction des eXtensible Messaging et présence protocole XMPP ().</span><span class="sxs-lookup"><span data-stu-id="8e99d-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="8e99d-106">Une configuration XMPP permet aux utilisateurs d’accéder à des utilisateurs de domaine XMPP par :</span><span class="sxs-lookup"><span data-stu-id="8e99d-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="8e99d-107">Messagerie instantanée et présence - personne à personne uniquement</span><span class="sxs-lookup"><span data-stu-id="8e99d-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="8e99d-108">Création de contacts fédérés XMPP dans le Skype pour client d’entreprise</span><span class="sxs-lookup"><span data-stu-id="8e99d-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="8e99d-109">Lorsque vous configurez les stratégies de prise en charge de XMPP les partenaires fédérés, les stratégies s’appliquent aux utilisateurs des domaines XMPP fédéré, mais pas aux utilisateurs de protocole d’ouverture de session (SIP) (IM) service de messagerie instantanée fournisseurs ou SIP des domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="8e99d-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="8e99d-110">Vous configurez un partenaire fédéré XMPP pour chaque domaine fédéré XMPP que vous souhaitez autoriser les utilisateurs à ajouter des contacts et communiquez avec.</span><span class="sxs-lookup"><span data-stu-id="8e99d-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="8e99d-111">Une fois que les stratégies sont en place, vous devez configurer les certificats de passerelle XMPP.</span><span class="sxs-lookup"><span data-stu-id="8e99d-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8e99d-112">La fonctionnalité XMPP est déconseillée dans Skype pour Business Server 2019, mais peut être poursuivie dans un serveur hérité en coexistence avec Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8e99d-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="8e99d-113">Assurez-vous que vous avez déjà déployé le serveur hérité (Skype pour Business Server 2015 / Lync Server 2013), la passerelle XMPP et configuré les stratégies d’accès pour permettre aux utilisateurs pour la passerelle XMPP hérité.</span><span class="sxs-lookup"><span data-stu-id="8e99d-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="8e99d-114">Pour plus d’informations, consultez la rubrique [Migrer la fédération XMPP](migrating-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="8e99d-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="8e99d-115">Configurer une stratégie d’accès externe pour activer des utilisateurs pour la passerelle XMPP hérité</span><span class="sxs-lookup"><span data-stu-id="8e99d-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="8e99d-116">Ouvrez le Skype hérité pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="8e99d-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="8e99d-117">Dans la barre de navigation de gauche, cliquez sur **fédération et accès externe**, puis cliquez sur **Stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="8e99d-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="8e99d-118">Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="8e99d-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="8e99d-119">Entrez un nom pour la stratégie utilisateur d’accès externe.</span><span class="sxs-lookup"><span data-stu-id="8e99d-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="8e99d-120">Fournissez une description pour la stratégie utilisateur d’accès externe.</span><span class="sxs-lookup"><span data-stu-id="8e99d-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="8e99d-121">Sélectionnez **Activer les communications avec les utilisateurs fédérés**.</span><span class="sxs-lookup"><span data-stu-id="8e99d-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="8e99d-122">Sélectionnez **Autoriser les communications avec XMPP des utilisateurs fédérés**.</span><span class="sxs-lookup"><span data-stu-id="8e99d-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="8e99d-123">Cliquez sur **Valider** pour enregistrer vos modifications à la stratégie de site ou utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8e99d-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

