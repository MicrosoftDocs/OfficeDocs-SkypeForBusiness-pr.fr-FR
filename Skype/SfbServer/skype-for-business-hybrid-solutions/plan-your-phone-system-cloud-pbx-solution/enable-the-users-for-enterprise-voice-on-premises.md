---
title: Activer les utilisateurs pour Voix Entreprise sur site
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Pour qu’un utilisateur utilise le système téléphonique (PBX cloud), vous devez d’abord l’activer Voix Entreprise lui attribuer un numéro de téléphone. Pour ce faire, utilisez votre déploiement local alors que l’utilisateur est toujours dos au déploiement local.
ms.openlocfilehash: 7fc629114900cb9f4d825bd8fdc8e946e6c63880
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359190"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="7e572-104">Activer les utilisateurs pour Voix Entreprise sur site</span><span class="sxs-lookup"><span data-stu-id="7e572-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="7e572-105">Pour qu’un utilisateur utilise le système téléphonique (PBX cloud), vous devez d’abord l’activer Voix Entreprise lui attribuer un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="7e572-105">For a user to use Phone System (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="7e572-106">Pour ce faire, utilisez votre déploiement local alors que l’utilisateur est toujours dos au déploiement local.</span><span class="sxs-lookup"><span data-stu-id="7e572-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>

> [!Important]
> <span data-ttu-id="7e572-107">Skype Entreprise Online sera retiré le 31 juillet 2021, après quoi le service ne sera plus accessible.</span><span class="sxs-lookup"><span data-stu-id="7e572-107">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="7e572-108">En outre, la connectivité PSTN entre votre environnement local via Skype Entreprise Server ou Cloud Connector Edition et Skype Entreprise Online ne sera plus prise en charge.</span><span class="sxs-lookup"><span data-stu-id="7e572-108">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="7e572-109">Découvrez comment connecter votre réseau téléphonique local à Teams à l’aide du [routage direct.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="7e572-109">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="7e572-110">Pour activer un utilisateur pour Voix Entreprise local et affecter un numéro de téléphone</span><span class="sxs-lookup"><span data-stu-id="7e572-110">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="7e572-111">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="7e572-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7e572-112">Utilisez le menu Démarrer ou le raccourci bureau pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7e572-112">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="7e572-113">Vous pouvez également ouvrir une fenêtre de navigateur, puis entrer l’URL de l’administrateur pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7e572-113">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="7e572-114">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="7e572-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="7e572-115">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="7e572-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="7e572-116">Dans le tableau, cliquez sur le compte d’utilisateur Skype Entreprise Online que vous souhaitez activer pour Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="7e572-116">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="7e572-117">Dans le menu **Edition,** cliquez **sur Afficher les détails.**</span><span class="sxs-lookup"><span data-stu-id="7e572-117">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="7e572-118">Sous **Téléphonie,** cliquez **sur Voix Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="7e572-118">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="7e572-119">Cliquez **sur URI** de ligne et tapez un numéro de téléphone unique et normal (par exemple, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="7e572-119">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="7e572-120">Cliquez ensuite sur **Valider.**</span><span class="sxs-lookup"><span data-stu-id="7e572-120">Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="7e572-121">Considérations spéciales lors de l’activation des utilisateurs Voix Entreprise sur site</span><span class="sxs-lookup"><span data-stu-id="7e572-121">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="7e572-122">Dans certains cas, vous devrez peut-être modifier la façon dont vous activez les utilisateurs pour Voix Entreprise afin de vous assurer qu’ils peuvent correctement effectuer et recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="7e572-122">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="7e572-123">Si votre déploiement compte des utilisateurs qui répondent aux conditions suivantes, effectuez les étapes incluses pour activer l’utilisateur pour Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="7e572-123">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="7e572-124">Si un utilisateur est créé dans votre AD local, puis synchronisé avec Skype Entreprise Online sans être activé pour Skype Entreprise ou pour Voix Entreprise et que vous n’avez pas de lineURI, exécutez les cmdlets suivantes pour chaque utilisateur concerné, en remplaçant les valeurs par les valeurs réelles de votre environnement \< \> :</span><span class="sxs-lookup"><span data-stu-id="7e572-124">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="7e572-125">Si un utilisateur est déjà activé pour Skype Entreprise en local, mais qu’il n’a pas été activé pour Voix Entreprise ou qu’un lineURI n’a pas été affecté avant d’être déplacé vers Skype Entreprise Online, exécutez l’cmdlet suivante pour chaque utilisateur :</span><span class="sxs-lookup"><span data-stu-id="7e572-125">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="7e572-126">Si un utilisateur est déjà activé dans Skype Entreprise sur site, mais n’est pas activé pour Voix Entreprise, même s’il a déjà affecté un LineURI, exécutez l’cmdlet suivante pour chaque utilisateur concerné :</span><span class="sxs-lookup"><span data-stu-id="7e572-126">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


