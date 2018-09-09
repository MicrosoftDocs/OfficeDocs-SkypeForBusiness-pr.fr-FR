---
title: Activer les utilisateurs pour Enterprise Voice sur site
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Pour un utilisateur à utiliser le système téléphonique dans Office 365 (en nuage PBX), vous devez tout d’abord les activer pour Enterprise Voice et affecter un numéro de téléphone. Cela à l’aide de votre déploiement sur site pendant que l’utilisateur est toujours hébergé dans le déploiement local.
ms.openlocfilehash: 8d00120b0b0fd74baed1ceb003a46cfc2468d502
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883375"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="4a94c-104">Activer les utilisateurs pour Enterprise Voice sur site</span><span class="sxs-lookup"><span data-stu-id="4a94c-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="4a94c-105">Pour un utilisateur à utiliser le système téléphonique dans Office 365 (en nuage PBX), vous devez tout d’abord les activer pour Enterprise Voice et affecter un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="4a94c-105">For a user to use Phone System in Office 365 (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="4a94c-106">Cela à l’aide de votre déploiement sur site pendant que l’utilisateur est toujours hébergé dans le déploiement local.</span><span class="sxs-lookup"><span data-stu-id="4a94c-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="4a94c-107">Pour activer un utilisateur pour Enterprise Voice sur site et affecter un numéro de téléphone</span><span class="sxs-lookup"><span data-stu-id="4a94c-107">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="4a94c-108">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4a94c-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4a94c-109">Utilisez le menu Démarrer ou le raccourci bureau pour ouvrir le Panneau de configuration de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="4a94c-109">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="4a94c-110">Vous pouvez également ouvrir une fenêtre de navigateur, puis saisir l’URL de l’administrateur pour ouvrir le Panneau de configuration de Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4a94c-110">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="4a94c-111">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="4a94c-111">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="4a94c-112">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="4a94c-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="4a94c-113">Dans le tableau, cliquez sur le Skype Business en ligne compte d’utilisateur que vous souhaitez activer pour Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="4a94c-113">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="4a94c-114">Dans le menu **Modifier**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="4a94c-114">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="4a94c-115">Sous **Téléphonie**, cliquez sur **Voix Entreprise**.</span><span class="sxs-lookup"><span data-stu-id="4a94c-115">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="4a94c-p103">Cliquez sur l’**URI de ligne**, puis saisissez un numéro de téléphone normalisé unique (par exemple, tél :+14255550200). Ensuite, cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="4a94c-p103">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200). Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="4a94c-118">Considérations particulières lors de l’activation des utilisateurs pour Enterprise Voice sur site</span><span class="sxs-lookup"><span data-stu-id="4a94c-118">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="4a94c-119">Dans certains cas, vous devrez peut-être modifier la façon d’activer les utilisateurs pour Voix Entreprise de sorte qu’ils puissent passer et recevoir des appels de manière appropriée.</span><span class="sxs-lookup"><span data-stu-id="4a94c-119">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="4a94c-120">Si vous avez des utilisateurs qui répondent aux conditions suivantes dans votre déploiement, effectuez les étapes incluses pour permettre à l’utilisateur pour Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="4a94c-120">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="4a94c-121">Si un utilisateur est créé dans votre environnement local AD synchronisé avec Skype pour Business Online sans être activé pour Skype pour les entreprises ou pour Enterprise Voice et n’ont pas LineURI définir, exécutez les applets de commande suivantes pour chaque utilisateur concerné, en remplaçant les valeurs < C0 > <b1></b1> par des valeurs réelles pour votre environnement :</span><span class="sxs-lookup"><span data-stu-id="4a94c-121">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="4a94c-122">Si un utilisateur est déjà activé pour Skype pour les entreprises dans les locaux, mais a été pas activé pour Enterprise Voice ou affecté LineURI avant d’être déplacés à Skype pour Business Online, exécutez l’applet de commande suivante pour chaque utilisateur :</span><span class="sxs-lookup"><span data-stu-id="4a94c-122">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="4a94c-123">Si un utilisateur est déjà activé dans Skype pour les entreprises dans les locaux, mais pas activé pour Enterprise Voice, même si déjà affecté un LineURI, exécutez la cmdlet suivante pour chaque utilisateur affecté :</span><span class="sxs-lookup"><span data-stu-id="4a94c-123">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


