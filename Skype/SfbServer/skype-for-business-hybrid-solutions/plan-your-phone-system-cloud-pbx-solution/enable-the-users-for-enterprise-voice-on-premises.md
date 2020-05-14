---
title: Activer les utilisateurs pour voix entreprise sur site
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
description: Pour qu’un utilisateur utilise le système téléphonique (PBX Cloud), vous devez d’abord l’activer pour voix entreprise et lui attribuer un numéro de téléphone. Pour ce faire, utilisez votre déploiement local pendant que l’utilisateur est toujours hébergé dans le déploiement local.
ms.openlocfilehash: f02638f618b32190fafcded66550b5c3dcc52f2d
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221698"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="7ab80-104">Activer les utilisateurs pour voix entreprise sur site</span><span class="sxs-lookup"><span data-stu-id="7ab80-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="7ab80-105">Pour qu’un utilisateur utilise le système téléphonique (PBX Cloud), vous devez d’abord l’activer pour voix entreprise et lui attribuer un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="7ab80-105">For a user to use Phone System (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="7ab80-106">Pour ce faire, utilisez votre déploiement local pendant que l’utilisateur est toujours hébergé dans le déploiement local.</span><span class="sxs-lookup"><span data-stu-id="7ab80-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="7ab80-107">Pour activer un utilisateur pour voix entreprise sur site et attribuer un numéro de téléphone</span><span class="sxs-lookup"><span data-stu-id="7ab80-107">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="7ab80-108">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="7ab80-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7ab80-109">Utilisez le menu Démarrer ou le raccourci Bureau pour ouvrir le panneau de configuration de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7ab80-109">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="7ab80-110">Vous pouvez également ouvrir une fenêtre de navigateur, puis entrer l’URL de l’administrateur pour ouvrir le panneau de configuration de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7ab80-110">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="7ab80-111">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="7ab80-111">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="7ab80-112">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="7ab80-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="7ab80-113">Dans le tableau, cliquez sur le compte d’utilisateur Skype entreprise Online que vous souhaitez activer pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="7ab80-113">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="7ab80-114">Dans le menu **Edition** , cliquez sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="7ab80-114">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="7ab80-115">Sous **téléphonie**, cliquez sur **voix entreprise**.</span><span class="sxs-lookup"><span data-stu-id="7ab80-115">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="7ab80-116">Cliquez sur **URI de ligne**, puis tapez un numéro de téléphone normalisé unique (par exemple, tel : + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="7ab80-116">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="7ab80-117">Ensuite, cliquez sur **valider**.</span><span class="sxs-lookup"><span data-stu-id="7ab80-117">Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="7ab80-118">Considérations particulières lors de l’activation des utilisateurs pour voix entreprise sur site</span><span class="sxs-lookup"><span data-stu-id="7ab80-118">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="7ab80-119">Dans certains cas, vous devrez peut-être modifier la façon dont vous activez les utilisateurs pour voix entreprise afin de vous assurer qu’ils peuvent passer et recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="7ab80-119">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="7ab80-120">Si des utilisateurs de votre déploiement remplissent les conditions suivantes, effectuez les étapes requises pour activer l’utilisateur pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="7ab80-120">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="7ab80-121">Si un utilisateur est créé dans votre AD sur site, puis synchronisé avec Skype entreprise Online sans être activé pour Skype entreprise ou pour voix entreprise et n’ont pas de jeu LineURI, exécutez les applets de commande suivantes pour chaque utilisateur affecté, en remplaçant les valeurs par les \< \> valeurs réelles de votre environnement :</span><span class="sxs-lookup"><span data-stu-id="7ab80-121">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="7ab80-122">Si un utilisateur est déjà activé pour Skype entreprise en local, mais n’a pas été activé pour voix entreprise ou s’il a été affecté à un LineURI avant d’être déplacé vers Skype entreprise Online, exécutez l’applet de commande suivante pour chaque utilisateur :</span><span class="sxs-lookup"><span data-stu-id="7ab80-122">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="7ab80-123">Si un utilisateur est déjà activé dans Skype entreprise en local, mais n’est pas activé pour voix entreprise, même si un LineURI a déjà été affecté, exécutez l’applet de commande suivante pour chaque utilisateur concerné :</span><span class="sxs-lookup"><span data-stu-id="7ab80-123">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


