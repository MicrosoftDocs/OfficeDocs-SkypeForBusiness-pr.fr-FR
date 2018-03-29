---
title: Remarques relatives à la jonction du domaine Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Consultez cette rubrique pour découvrir comment joindre un appareil PC Skype Room System à votre domaine.
ms.openlocfilehash: 93aa983080ee93f38143224b6c74bdcd6490842c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="6a8a9-103">Remarques relatives à la jonction du domaine Skype Room System</span><span class="sxs-lookup"><span data-stu-id="6a8a9-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="6a8a9-104">Consultez cette rubrique pour découvrir comment joindre un appareil PC Skype Room System à votre domaine.</span><span class="sxs-lookup"><span data-stu-id="6a8a9-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="6a8a9-105">Remarques relatives à la jonction du domaine</span><span class="sxs-lookup"><span data-stu-id="6a8a9-105">Domain joining considerations</span></span>

<span data-ttu-id="6a8a9-106">Vous pouvez joindre la solution matérielle-logicielle Skype espace système PC au domaine Active Directory ou le laisser dans un groupe de travail.</span><span class="sxs-lookup"><span data-stu-id="6a8a9-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="6a8a9-107">Tenez compte des points suivants avant cette décision :</span><span class="sxs-lookup"><span data-stu-id="6a8a9-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="6a8a9-108">Domaine-joindre la solution matérielle-logicielle Skype espace système PC permet d’importer automatiquement des chaîne de certificat de racine privée de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6a8a9-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="6a8a9-109">Domaine-joindre la solution matérielle-logicielle Skype espace système PC vous permet d’accorder aux utilisateurs du domaine et des droits d’administration des groupes.</span><span class="sxs-lookup"><span data-stu-id="6a8a9-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="6a8a9-110">En procédant ainsi, vous n’aurez pas à retenir le mot de passe du compte administrateur au niveau de l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="6a8a9-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="6a8a9-111">Lorsque vous joignez une solution matérielle-logicielle Skype espace système PC sur le domaine, il est nécessaire que vous créez une autre unité d’organisation (OU), afin que vous puissiez fournir des exclusions de l’objet de stratégie de groupe (GPO) pour l’unité d’organisation dans lequel tous les objets d’ordinateur Skype espace système résident.</span><span class="sxs-lookup"><span data-stu-id="6a8a9-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="6a8a9-112">Lorsque vous effectuez cette opération, créez les objets ordinateur dans l’unité d’organisation avant de joindre la solution matérielle-logicielle Skype espace système PC sur le domaine.</span><span class="sxs-lookup"><span data-stu-id="6a8a9-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="6a8a9-113">De nombreuses organisations possèdent les objets stratégie de groupe, qui affectent des fonctions du matériel PC système de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="6a8a9-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="6a8a9-114">Assurez-vous que vous substituez ou bloquez l’héritage de ces objets de stratégie de groupe dans l’unité d’organisation du système de salle de Skype :</span><span class="sxs-lookup"><span data-stu-id="6a8a9-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="6a8a9-115">Délai d’ouverture de sessions (verrouillage automatique)</span><span class="sxs-lookup"><span data-stu-id="6a8a9-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="6a8a9-116">Stratégies connexes de gestion de l’alimentation</span><span class="sxs-lookup"><span data-stu-id="6a8a9-116">Power management related policies</span></span>
    
  - <span data-ttu-id="6a8a9-117">Besoin d’étapes d’authentification supplémentaires</span><span class="sxs-lookup"><span data-stu-id="6a8a9-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="6a8a9-118">Accès aux lecteurs locaux refusé</span><span class="sxs-lookup"><span data-stu-id="6a8a9-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="6a8a9-119">Inviter les utilisateurs à des connexions réseau lentes</span><span class="sxs-lookup"><span data-stu-id="6a8a9-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="6a8a9-120">Démarrer un programme donné à l’ouverture</span><span class="sxs-lookup"><span data-stu-id="6a8a9-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="6a8a9-121">Créer un autre compte d’utilisateur de domaine sur tous les ordinateurs liés au domaine.</span><span class="sxs-lookup"><span data-stu-id="6a8a9-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="6a8a9-122">Pousser la mise à jour de Windows pour système de salle de Skype</span><span class="sxs-lookup"><span data-stu-id="6a8a9-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="6a8a9-123">En guise d’alternative, vous pouvez décider de laisser l’appareil PC dans le groupe de travail.</span><span class="sxs-lookup"><span data-stu-id="6a8a9-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="6a8a9-124">Comme avec le bureau Skype pour client d’entreprise, vous devez importer manuellement la chaîne de certificats racine sur la solution matérielle-logicielle Skype espace système PC.</span><span class="sxs-lookup"><span data-stu-id="6a8a9-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="6a8a9-125">Vous ne devez pas importer la chaîne de certificats racine si votre Skype pour le déploiement de l’entreprise utilise un certificat public (par exemple, Entrust, VeriSign et ainsi de suite).</span><span class="sxs-lookup"><span data-stu-id="6a8a9-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="6a8a9-126">Si vous envisagez de rejoindre les machines Skype espace système au domaine, pour éviter l’assemblage machine de Skype espace système par inadvertance à une unité d’organisation inattendue, qui ne peut être exempte de la stratégie de groupe, vérifiez que vous participez à l’unité d’organisation correcte.</span><span class="sxs-lookup"><span data-stu-id="6a8a9-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="6a8a9-127">Vous permet de l’applet de commande suivante à partir de l’ordinateur système d’espace Skype pour jointure dans l’unité d’organisation correcte et ne reçoit pas d’objets de stratégie de groupe susceptibles de bloquer la fonctionnalité LRS.</span><span class="sxs-lookup"><span data-stu-id="6a8a9-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="6a8a9-128">Contactez votre administrateur système ou partenaire OEM pour exécuter ces applets de commande :</span><span class="sxs-lookup"><span data-stu-id="6a8a9-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"

```

<span data-ttu-id="6a8a9-129">Même si vous créez une unité organisationnelle distincte et que vous bloquez l’héritage, il existe certaines stratégies qui pourraient entraîner des problèmes à un niveau supérieur.</span><span class="sxs-lookup"><span data-stu-id="6a8a9-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="6a8a9-130">Une stratégie de groupe sans aucun paramètre de remplacement bat une unité organisationnelle avec un paramètre Bloquer l’héritage de stratégies.</span><span class="sxs-lookup"><span data-stu-id="6a8a9-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="6a8a9-131">Pour plus d’informations, consultez l’article « N° substituer par rapport sur Bloquer l’héritage » dans la documentation de la stratégie de groupe à http://technet.microsoft.com/en-us/library/cc978255.aspx.</span><span class="sxs-lookup"><span data-stu-id="6a8a9-131">For more information, see the article "No Override as Compared to Block Policy Inheritance" in the Group Policy documentation at http://technet.microsoft.com/en-us/library/cc978255.aspx.</span></span>
  
<span data-ttu-id="6a8a9-132">Vous avez peut-être plusieurs approches pour résoudre ces problèmes.</span><span class="sxs-lookup"><span data-stu-id="6a8a9-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="6a8a9-133">Nous vous conseillons de consulter vos experts Active Directory afin de vous assurer que vous disposez d’une unité organisationnelle aux paramètres GPO appropriés, ou au moins d’une unité organisationnelle dans laquelle les stratégies décrites précédemment n’existent pas.</span><span class="sxs-lookup"><span data-stu-id="6a8a9-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="6a8a9-134">Il est conseillé d’activer la qualité de Service (QoS) pour système de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="6a8a9-134">It is advised to enable Quality of Service (QoS) for Skype Room System.</span></span>
  

