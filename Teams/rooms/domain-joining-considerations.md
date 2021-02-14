---
title: Remarques relatives à la jonction du domaine Skype Room System
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: L’administrateur peut découvrir comment joindre un PC d’appliance PC Skype Room System à un domaine Active Directory, ainsi que les considérations à prendre en considération.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfcee1421c25903a5ec8deb2f66871ed1d57ef1c
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905436"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="51948-103">Remarques relatives à la jonction du domaine Skype Room System</span><span class="sxs-lookup"><span data-stu-id="51948-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="51948-104">Consultez cette rubrique pour découvrir comment joindre un appareil PC Skype Room System à votre domaine.</span><span class="sxs-lookup"><span data-stu-id="51948-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="51948-105">Remarques relatives à la jonction du domaine</span><span class="sxs-lookup"><span data-stu-id="51948-105">Domain joining considerations</span></span>

<span data-ttu-id="51948-106">Vous pouvez joindre l’appliance PC de Skype Room System au domaine Active Directory ou le laisser dans un groupe de travail.</span><span class="sxs-lookup"><span data-stu-id="51948-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="51948-107">Tenez compte des points suivants avant cette décision :</span><span class="sxs-lookup"><span data-stu-id="51948-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="51948-108">Le fait de joindre un domaine à l’appliance PC de Skype Room System permet d’importer automatiquement la chaîne de certificats racine privé de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="51948-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
- <span data-ttu-id="51948-109">Le fait de rejoindre un domaine sur l’appliance PC de Skype Room System vous permet d’accorder à des utilisateurs de domaine et à des groupes des droits d’administration.</span><span class="sxs-lookup"><span data-stu-id="51948-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="51948-110">En procédant ainsi, vous n’aurez pas à retenir le mot de passe du compte administrateur au niveau de l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="51948-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
- <span data-ttu-id="51948-111">Lorsque vous joignez un PC d’appliance Skype Room System au domaine, vous devez créer une unité organisationnelle distincte afin de pouvoir fournir des exclusions d’objets de stratégie de groupe à l’unité d’organisation où se trouvent tous les objets machine Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="51948-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="51948-112">Dans ce cas, créez des objets machine dans l’ou avant de joindre le PC d’appliance Skype Room System au domaine.</span><span class="sxs-lookup"><span data-stu-id="51948-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
- <span data-ttu-id="51948-113">De nombreuses organisations ont les fonctions de groupe suivantes, qui affectent les fonctions d’appliance PC de Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="51948-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="51948-114">Assurez-vous de remplacer ou de bloquer l’héritage de ces éléments de groupe dans le système de salle Skype ou :</span><span class="sxs-lookup"><span data-stu-id="51948-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span>

  - <span data-ttu-id="51948-115">Délai d’ouverture de sessions (verrouillage automatique)</span><span class="sxs-lookup"><span data-stu-id="51948-115">Timeout of logon sessions (auto lockout)</span></span>
  - <span data-ttu-id="51948-116">Stratégies connexes de gestion de l’alimentation</span><span class="sxs-lookup"><span data-stu-id="51948-116">Power management related policies</span></span>
  - <span data-ttu-id="51948-117">Besoin d’étapes d’authentification supplémentaires</span><span class="sxs-lookup"><span data-stu-id="51948-117">Requiring additional authentication steps</span></span>
  - <span data-ttu-id="51948-118">Accès aux lecteurs locaux refusé</span><span class="sxs-lookup"><span data-stu-id="51948-118">Denying access to local drives</span></span>
  - <span data-ttu-id="51948-119">Inviter les utilisateurs à des connexions réseau lentes</span><span class="sxs-lookup"><span data-stu-id="51948-119">Prompting users for slow network connections</span></span>
  - <span data-ttu-id="51948-120">Démarrer un programme donné à l’ouverture</span><span class="sxs-lookup"><span data-stu-id="51948-120">Start a certain program at logon</span></span>
  - <span data-ttu-id="51948-121">Créer un autre compte d’utilisateur de domaine sur tous les ordinateurs liés au domaine.</span><span class="sxs-lookup"><span data-stu-id="51948-121">Create another domain user account on all domain-joined machines.</span></span>
  - <span data-ttu-id="51948-122">Push Windows Update to Skype Room System</span><span class="sxs-lookup"><span data-stu-id="51948-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="51948-123">En guise d’alternative, vous pouvez décider de laisser l’appareil PC dans le groupe de travail.</span><span class="sxs-lookup"><span data-stu-id="51948-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="51948-124">Comme pour le client de bureau Microsoft Teams ou Skype Entreprise, vous devez importer manuellement la chaîne de certificats racine sur l’appliance PC de l’appliance Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="51948-124">As with the desktop Microsoft Teams or Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="51948-125">Vous n’êtes pas obligé d’importer la chaîne de certificats racine si votre déploiement utilise un certificat public (par exemple, Confie, VeriSign, et ainsi de suite).</span><span class="sxs-lookup"><span data-stu-id="51948-125">You're not required to import the root certificate chain if your deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="51948-126">Si vous envisagez d’associer des ordinateurs Skype Room System au domaine, pour éviter de rejoindre l’ordinateur Skype Room System par inadvertance à une ou plusieurs personnes non souhaitées, qui ne sont peut-être pas libres des noms de groupe, assurez-vous de participer à l’ou ou correcte.</span><span class="sxs-lookup"><span data-stu-id="51948-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="51948-127">Vous pouvez utiliser l’cmdlet suivante à partir de l’ordinateur Skype Room System pour rejoindre le système d’exploitation correct et ne recevez pas d’os de stratégie de groupe qui peuvent bloquer la fonctionnalité LRS.</span><span class="sxs-lookup"><span data-stu-id="51948-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="51948-128">Contactez votre administrateur système ou partenaire OEM pour exécuter ces applets de commande :</span><span class="sxs-lookup"><span data-stu-id="51948-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="51948-129">Même si vous créez une unité organisationnelle distincte et que vous bloquez l’héritage, il existe certaines stratégies qui pourraient entraîner des problèmes à un niveau supérieur.</span><span class="sxs-lookup"><span data-stu-id="51948-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="51948-130">Une stratégie de groupe sans aucun paramètre de remplacement bat une unité organisationnelle avec un paramètre Bloquer l’héritage de stratégies.</span><span class="sxs-lookup"><span data-stu-id="51948-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="51948-131">Pour plus d’informations, voir [l’article](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) Non remplacer comparé à Bloquer l’héritage de stratégie dans la documentation sur les stratégies de groupe.</span><span class="sxs-lookup"><span data-stu-id="51948-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="51948-132">Vous avez peut-être plusieurs approches pour résoudre ces problèmes.</span><span class="sxs-lookup"><span data-stu-id="51948-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="51948-133">Nous vous conseillons de consulter vos experts Active Directory afin de vous assurer que vous disposez d’une unité organisationnelle aux paramètres GPO appropriés, ou au moins d’une unité organisationnelle dans laquelle les stratégies décrites précédemment n’existent pas.</span><span class="sxs-lookup"><span data-stu-id="51948-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="51948-134">Il est recommandé d’activer la qualité de service (QoS) pour les appareils Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="51948-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="51948-135">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="51948-135">Related topics</span></span>
  
[<span data-ttu-id="51948-136">Configuration du périphérique : création d’un périphérique ou modification d’un périphérique existant</span><span class="sxs-lookup"><span data-stu-id="51948-136">Device Configuration: Create New or Edit Existing</span></span>](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="51948-137">Gestion de la qualité de service</span><span class="sxs-lookup"><span data-stu-id="51948-137">Managing Quality of Service</span></span>](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
