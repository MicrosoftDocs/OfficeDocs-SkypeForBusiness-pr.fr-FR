---
title: Créer des administrateurs du Panneau de configuration Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour accorder l’accès à la Skype pour Business Server, procédez comme suit :'
ms.openlocfilehash: 5251a70cc76157731d96032a2e6631e795b64cf0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893685"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a><span data-ttu-id="d97eb-103">Créer des administrateurs du Panneau de configuration Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d97eb-103">Create Skype for Business Server Control Panel Administrators</span></span>
 
<span data-ttu-id="d97eb-104">Pour accorder l’accès à la Skype pour Business Server, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="d97eb-104">To grant access to the Skype for Business Server, do the following:</span></span>
  
1. <span data-ttu-id="d97eb-105">Ouvrez une session en tant que membre du groupe Administrateurs du domaine ou du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d97eb-105">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="d97eb-106">Ouvrez **Utilisateurs et ordinateurs Active Directory**, développez votre domaine, cliquez avec le bouton droit sur le conteneur **Utilisateurs**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d97eb-106">Open **Active Directory Users and Computers**, expand your domain, right-click the **Users** container, and then click **Properties**.</span></span>
    
3. <span data-ttu-id="d97eb-107">Dans **Propriétés de CSAdministrator**, cliquez sur l’onglet **Membres**.</span><span class="sxs-lookup"><span data-stu-id="d97eb-107">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
4. <span data-ttu-id="d97eb-p101">Sous l’onglet Membres, cliquez sur **Ajouter**. Dans **Sélectionner des utilisateurs, des contacts, des ordinateurs, des comptes de service ou des groupes**, recherchez **Entrez les noms des objets à sélectionner**. Tapez le ou les noms d’utilisateur ou de groupe à ajouter au groupe CSAdministrators. Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d97eb-p101">On the Members tab, click **Add**. In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**. Type the user name(s) or group name(s) to add to the group CSAdministrators. Click **OK**.</span></span>
    
5. <span data-ttu-id="d97eb-p102">Sous l’onglet Membre, confirmez que les utilisateurs ou les groupes que vous avez sélectionnés sont présents. Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d97eb-p102">On the Members tab, confirm that the users or groups that you selected are present. Click **OK**.</span></span>
    
> [!TIP]
> <span data-ttu-id="d97eb-114">Le Skype pour Business Server Control Panel est un outil de contrôle d’accès basé sur un rôle.</span><span class="sxs-lookup"><span data-stu-id="d97eb-114">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="d97eb-115">L’appartenance au groupe CsAdministrator donne à un utilisateur qui utilise le Skype pour contrôle total Business Server Control Panel pour toutes les fonctions de configuration disponibles.</span><span class="sxs-lookup"><span data-stu-id="d97eb-115">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all the configuration functions available.</span></span> <span data-ttu-id="d97eb-116">D’autres rôles conçus pour des fonctions spécifiques sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="d97eb-116">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="d97eb-117">Utilisateurs n’ont pas être activé pour Skype pour Business Server afin de devenir membres des groupes d’administration.</span><span class="sxs-lookup"><span data-stu-id="d97eb-117">Users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
<span data-ttu-id="d97eb-118">Autres rôles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="d97eb-118">Other roles include:</span></span>
  
- <span data-ttu-id="d97eb-119">**CsArchiving :** Membres de ce groupe peuvent effectuer toutes les fonctions d’archivage, comme la configuration et la gestion du rôle de serveur d’archivage.</span><span class="sxs-lookup"><span data-stu-id="d97eb-119">**CsArchiving:** Members of this group can perform all archiving functions, such as configuring and managing the Archiving Server role.</span></span>
    
- <span data-ttu-id="d97eb-p104">**CsHelpDesk :** les membres de ce groupe peuvent afficher la configuration et le déploiement, y compris les propriétés et stratégies d’utilisateurs. Ils peuvent également effectuer des tâches de dépannage spécifiques.</span><span class="sxs-lookup"><span data-stu-id="d97eb-p104">**CsHelpDesk:** Members of this group can view the configuration and deployment, including user properties and policies. Members can also perform specific troubleshooting tasks.</span></span>
    
- <span data-ttu-id="d97eb-p105">**CsLocationAdministrator :** les membres de ce groupe disposent des droits d’utilisateur les moins élevés associés à la gestion du système Enhanced 9-1-1 (E9-1-1). Ils peuvent créer des identificateurs de réseau et des emplacements E9-1-1 et les associer dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="d97eb-p105">**CsLocationAdministrator:** Members have the lowest level of user rights associated with Enhanced 9-1-1 (E9-1-1) management. They can create E9-1-1 locations and network identifiers and associate those in the deployment.</span></span>
    
- <span data-ttu-id="d97eb-124">**CsResponseGroupAdministrator :** les membres peuvent gérer et configurer le service Response Group.</span><span class="sxs-lookup"><span data-stu-id="d97eb-124">**CsResponseGroupAdministrator:** Members can manage and configure the Response Group service.</span></span>
    
- <span data-ttu-id="d97eb-125">**CsServerAdministrator :** Les membres peuvent gérer, surveiller et dépanner tous les serveurs exécutant Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="d97eb-125">**CsServerAdministrator:** Members can manage, monitor, and troubleshoot all servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="d97eb-126">**CsUserAdministrator :** les membres de ce groupe peuvent gérer, activer et désactiver des utilisateurs et assigner des stratégies existantes aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d97eb-126">**CsUserAdministrator:** Members can manage, enable and disable users, and assign existing policies to users.</span></span>
    
- <span data-ttu-id="d97eb-127">**CsViewOnlyAdministrator :** Les membres peuvent afficher le déploiement et la configuration des informations de serveur.</span><span class="sxs-lookup"><span data-stu-id="d97eb-127">**CsViewOnlyAdministrator:** Members can view the deployment and configuration of the server information.</span></span> <span data-ttu-id="d97eb-128">Cet abonnement permet à un membre afin de surveiller l’intégrité des serveurs exécutant Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="d97eb-128">This membership enables a member to monitor the health of the servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="d97eb-129">**CsVoiceAdministrator :** Les membres peuvent créer, configurer et gérer les paramètres de voix dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="d97eb-129">**CsVoiceAdministrator:** Members can create, configure, and manage voice-related settings in Skype for Business Server.</span></span>
    
<span data-ttu-id="d97eb-130">Pour préserver la sécurité et l’intégrité de contrôle d’accès basé sur un rôle, ajouter des utilisateurs aux groupes qui définissent le rôle tenu par l’utilisateur dans la gestion de la Skype pour le déploiement de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="d97eb-130">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span>
  

