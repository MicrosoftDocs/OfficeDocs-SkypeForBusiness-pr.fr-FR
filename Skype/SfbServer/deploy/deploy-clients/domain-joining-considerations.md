---
title: Remarques relatives à la jonction du domaine Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Consultez cette rubrique pour découvrir comment joindre un appareil PC Skype Room System à votre domaine.
ms.openlocfilehash: 2d2af20173708e199c1de5a205218d3295e7e0d3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234382"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="96389-103">Remarques relatives à la jonction du domaine Skype Room System</span><span class="sxs-lookup"><span data-stu-id="96389-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="96389-104">Consultez cette rubrique pour découvrir comment joindre un appareil PC Skype Room System à votre domaine.</span><span class="sxs-lookup"><span data-stu-id="96389-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="96389-105">Remarques relatives à la jonction du domaine</span><span class="sxs-lookup"><span data-stu-id="96389-105">Domain joining considerations</span></span>

<span data-ttu-id="96389-106">Vous pouvez rejoindre le PC de l’application Skype Room sur le domaine Active Directory ou la laisser dans un groupe de travail.</span><span class="sxs-lookup"><span data-stu-id="96389-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="96389-107">Tenez compte des points suivants avant cette décision :</span><span class="sxs-lookup"><span data-stu-id="96389-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="96389-108">La participation à un domaine avec l’application Skype Room System permet d’importer automatiquement la chaîne de certificats racine privés de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="96389-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="96389-109">La participation à un domaine avec l’application Skype Room System appliance vous permet d’accorder aux utilisateurs de domaine et aux groupes des droits d’administration.</span><span class="sxs-lookup"><span data-stu-id="96389-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="96389-110">En procédant ainsi, vous n’aurez pas à retenir le mot de passe du compte administrateur au niveau de l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="96389-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="96389-111">Lorsque vous rejoignez un ordinateur du système de salle Skype pour le domaine, vous devez créer une unité d’organisation (UO) distincte, afin de fournir des exclusions d’objets de stratégie de groupe à l’unité d’organisation où se trouvent tous les objets de l’ordinateur de bureau Skype.</span><span class="sxs-lookup"><span data-stu-id="96389-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="96389-112">Lorsque vous procédez ainsi, créez des objets machine dans l’unité d’organisation avant de joindre le PC du système de salle Skype au domaine.</span><span class="sxs-lookup"><span data-stu-id="96389-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="96389-113">De nombreuses organisations possèdent les objets de stratégie de groupe suivants qui concernent les fonctions PC de l’appliance de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="96389-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="96389-114">Assurez-vous de remplacer ou de bloquer l’héritage de ces objets de stratégie de groupe dans l’unité d’organisation de votre système de salle Skype:</span><span class="sxs-lookup"><span data-stu-id="96389-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="96389-115">Délai d’ouverture de sessions (verrouillage automatique)</span><span class="sxs-lookup"><span data-stu-id="96389-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="96389-116">Stratégies connexes de gestion de l’alimentation</span><span class="sxs-lookup"><span data-stu-id="96389-116">Power management related policies</span></span>
    
  - <span data-ttu-id="96389-117">Besoin d’étapes d’authentification supplémentaires</span><span class="sxs-lookup"><span data-stu-id="96389-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="96389-118">Accès aux lecteurs locaux refusé</span><span class="sxs-lookup"><span data-stu-id="96389-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="96389-119">Inviter les utilisateurs à des connexions réseau lentes</span><span class="sxs-lookup"><span data-stu-id="96389-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="96389-120">Démarrer un programme donné à l’ouverture</span><span class="sxs-lookup"><span data-stu-id="96389-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="96389-121">Créer un autre compte d’utilisateur de domaine sur tous les ordinateurs liés au domaine.</span><span class="sxs-lookup"><span data-stu-id="96389-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="96389-122">Diffuser Windows Update vers le système de salle Skype</span><span class="sxs-lookup"><span data-stu-id="96389-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="96389-123">En guise d’alternative, vous pouvez décider de laisser l’appareil PC dans le groupe de travail.</span><span class="sxs-lookup"><span data-stu-id="96389-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="96389-124">Comme pour le client de bureau Skype entreprise, vous devez importer manuellement la chaîne de certificats racine sur le PC du système de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="96389-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="96389-125">Vous n’êtes pas tenu d’importer la chaîne de certificats racines si votre déploiement Skype entreprise utilise un certificat public (par exemple, Entrust, VeriSign, etc.).</span><span class="sxs-lookup"><span data-stu-id="96389-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="96389-126">Si vous envisagez de joindre les machines de votre système de salle Skype à votre domaine, dans le cas d’une UO involontaire qui n’est pas disponible pour les objets de stratégie de groupe, assurez-vous de rejoindre l’UO correcte.</span><span class="sxs-lookup"><span data-stu-id="96389-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="96389-127">Vous pouvez utiliser l’applet de commande suivante depuis l’ordinateur système de salle Skype pour rejoindre l’UO correcte et ne pas recevoir d’objets de stratégie de groupe qui peuvent bloquer la fonctionnalité LRS.</span><span class="sxs-lookup"><span data-stu-id="96389-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="96389-128">Contactez votre administrateur système ou partenaire OEM pour exécuter ces applets de commande :</span><span class="sxs-lookup"><span data-stu-id="96389-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="96389-129">Même si vous créez une unité organisationnelle distincte et que vous bloquez l’héritage, il existe certaines stratégies qui pourraient entraîner des problèmes à un niveau supérieur.</span><span class="sxs-lookup"><span data-stu-id="96389-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="96389-130">Une stratégie de groupe sans aucun paramètre de remplacement bat une unité organisationnelle avec un paramètre Bloquer l’héritage de stratégies.</span><span class="sxs-lookup"><span data-stu-id="96389-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="96389-131">Pour plus d’informations, reportez-vous à l’article [aucun remplacement par rapport à l’héritage de la stratégie bloquer](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) dans la documentation de la stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="96389-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="96389-132">Vous avez peut-être plusieurs approches pour résoudre ces problèmes.</span><span class="sxs-lookup"><span data-stu-id="96389-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="96389-133">Nous vous conseillons de consulter vos experts Active Directory afin de vous assurer que vous disposez d’une unité organisationnelle aux paramètres GPO appropriés, ou au moins d’une unité organisationnelle dans laquelle les stratégies décrites précédemment n’existent pas.</span><span class="sxs-lookup"><span data-stu-id="96389-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="96389-134">Il est recommandé d’activer la qualité de service (QoS) pour les appareils système de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="96389-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="96389-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="96389-135">See also</span></span>
  
[<span data-ttu-id="96389-136">Configuration du périphérique : création d’un périphérique ou modification d’un périphérique existant</span><span class="sxs-lookup"><span data-stu-id="96389-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="96389-137">Gestion de la qualité de service</span><span class="sxs-lookup"><span data-stu-id="96389-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
