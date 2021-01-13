---
title: Considérations sur la jointation de domaine Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Lisez cette rubrique pour découvrir comment joindre un PC d’appliance Skype Room System à votre domaine.
ms.openlocfilehash: 6d6decf689b1a38615851911b42676050a823e4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805914"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="1ff00-103">Considérations sur la jointation de domaine Skype Room System</span><span class="sxs-lookup"><span data-stu-id="1ff00-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="1ff00-104">Lisez cette rubrique pour découvrir comment joindre un PC d’appliance Skype Room System à votre domaine.</span><span class="sxs-lookup"><span data-stu-id="1ff00-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="1ff00-105">Considérations sur la jonction de domaine</span><span class="sxs-lookup"><span data-stu-id="1ff00-105">Domain joining considerations</span></span>

<span data-ttu-id="1ff00-106">Vous pouvez joindre le PC appliance Skype Room System au domaine Active Directory ou le laisser dans un groupe de travail.</span><span class="sxs-lookup"><span data-stu-id="1ff00-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="1ff00-107">Prenez en compte les points suivants avant de prendre cette décision :</span><span class="sxs-lookup"><span data-stu-id="1ff00-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="1ff00-108">L’association de domaine à l’appliance PC Skype Room System permet d’importer automatiquement la chaîne de certificats racine privée de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1ff00-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="1ff00-109">La jointation de domaine à l’appareil PC Skype Room System vous permet d’accorder des droits d’administration aux utilisateurs de domaine et aux groupes.</span><span class="sxs-lookup"><span data-stu-id="1ff00-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="1ff00-110">Ainsi, vous n’aurez pas à mémoriser le mot de passe du compte d’administrateur au niveau de l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="1ff00-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="1ff00-111">Lorsque vous joignez un PC Appliance Skype Room System au domaine, vous devez créer une unité d’organisation distincte afin de pouvoir fournir des exclusions d’objets de stratégie de groupe à l’unité d’organisation où résident tous les objets ordinateur Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="1ff00-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="1ff00-112">Lorsque vous faites cela, créez des objets machine dans l’ou avant de joindre le PC appliance Skype Room System au domaine.</span><span class="sxs-lookup"><span data-stu-id="1ff00-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="1ff00-113">De nombreuses organisations ont les G GPO suivants, qui affectent les fonctions du PC appliance de Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="1ff00-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="1ff00-114">Assurez-vous que vous remplacez ou bloquez l’héritage de ces G GPO dans l’ou skype room system :</span><span class="sxs-lookup"><span data-stu-id="1ff00-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="1ff00-115">Délai d’ouverture de session (verrouillage automatique)</span><span class="sxs-lookup"><span data-stu-id="1ff00-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="1ff00-116">Stratégies liées à la gestion de l’alimentation</span><span class="sxs-lookup"><span data-stu-id="1ff00-116">Power management related policies</span></span>
    
  - <span data-ttu-id="1ff00-117">Exiger des étapes d’authentification supplémentaires</span><span class="sxs-lookup"><span data-stu-id="1ff00-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="1ff00-118">Refus d’accès aux lecteurs locaux</span><span class="sxs-lookup"><span data-stu-id="1ff00-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="1ff00-119">Invite des utilisateurs à des connexions réseau lentes</span><span class="sxs-lookup"><span data-stu-id="1ff00-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="1ff00-120">Démarrer un certain programme à l' logon</span><span class="sxs-lookup"><span data-stu-id="1ff00-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="1ff00-121">Créez un autre compte d’utilisateur de domaine sur tous les ordinateurs joints au domaine.</span><span class="sxs-lookup"><span data-stu-id="1ff00-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="1ff00-122">Push Windows Update to Skype Room System</span><span class="sxs-lookup"><span data-stu-id="1ff00-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="1ff00-123">Vous pouvez également décider de laisser l’appliance PC dans le groupe de travail.</span><span class="sxs-lookup"><span data-stu-id="1ff00-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="1ff00-124">Comme pour le client Skype Entreprise de bureau, vous devez importer manuellement la chaîne de certificats racine sur le PC d’appliance Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="1ff00-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="1ff00-125">Vous n’êtes pas obligé d’importer la chaîne de certificats racine si votre déploiement Skype Entreprise utilise un certificat public (par exemple, L’uri, VeriSign, et ainsi de suite).</span><span class="sxs-lookup"><span data-stu-id="1ff00-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="1ff00-126">Si vous envisagez de joindre des ordinateurs Skype Room System au domaine, afin d’éviter de joindre l’ordinateur Skype Room System par inadvertance à une ouo involontaire, qui n’est peut-être pas gratuite des GOP, assurez-vous que vous rejoignez l’ou correcte.</span><span class="sxs-lookup"><span data-stu-id="1ff00-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="1ff00-127">Vous pouvez utiliser l’cmdlet suivante à partir de l’ordinateur Skype Room System pour rejoindre l’ou correcte et ne reçoit pas les G STRATÉGIE de groupe qui peuvent bloquer la fonctionnalité LRS.</span><span class="sxs-lookup"><span data-stu-id="1ff00-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="1ff00-128">Contactez votre administrateur système ou votre partenaire OEM pour exécuter ces cmdlet :</span><span class="sxs-lookup"><span data-stu-id="1ff00-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="1ff00-129">Même si vous créez une ou plusieurs ou entités distinctes et bloquez l’héritage, certaines stratégies peuvent entraîner des problèmes à un niveau supérieur.</span><span class="sxs-lookup"><span data-stu-id="1ff00-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="1ff00-130">Une stratégie de groupe sans paramètre de remplacement remplace une ou une autre avec un paramètre Bloquer l’héritage des stratégies.</span><span class="sxs-lookup"><span data-stu-id="1ff00-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="1ff00-131">Pour plus d’informations, voir l’article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) dans la documentation de stratégie de groupe.</span><span class="sxs-lookup"><span data-stu-id="1ff00-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="1ff00-132">Vous pouvez avoir plusieurs approches pour résoudre ces problèmes.</span><span class="sxs-lookup"><span data-stu-id="1ff00-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="1ff00-133">Nous vous conseillons de consulter vos experts Active Directory pour vous assurer que vous disposez d’une ou de plusieurs ou de ces deux équipes, ou au moins d’une ou plusieurs de vos stratégies décrites précédemment.</span><span class="sxs-lookup"><span data-stu-id="1ff00-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="1ff00-134">Il est recommandé d’activer la qualité de service (QoS) pour les appareils Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="1ff00-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ff00-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1ff00-135">See also</span></span>
  
[<span data-ttu-id="1ff00-136">Configuration du périphérique : création d’un périphérique ou modification d’un périphérique existant</span><span class="sxs-lookup"><span data-stu-id="1ff00-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="1ff00-137">Gestion de la qualité de service</span><span class="sxs-lookup"><span data-stu-id="1ff00-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
