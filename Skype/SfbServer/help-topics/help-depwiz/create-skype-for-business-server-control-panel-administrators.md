---
title: Créer des administrateurs du Panneau de configuration Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: 'Pour octroyer l’accès à Skype entreprise Server 2015, procédez comme suit:'
ms.openlocfilehash: 6fe5fee80921121c71ccdc4bb6e6de29ac4302fb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301875"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a><span data-ttu-id="21f16-103">Créer des administrateurs du Panneau de configuration Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="21f16-103">Create Skype for Business Server Control Panel Administrators</span></span>
 
<span data-ttu-id="21f16-104">Pour octroyer l’accès à Skype entreprise Server 2015, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="21f16-104">To grant access to the Skype for Business Server 2015, do the following:</span></span>
  
1. <span data-ttu-id="21f16-105">Ouvrez une session en tant que membre du groupe Administrateurs du domaine ou du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="21f16-105">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="21f16-106">Ouvrez **Utilisateurs et ordinateurs Active Directory**, développez votre domaine, cliquez avec le bouton droit sur le conteneur **Utilisateurs**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="21f16-106">Open **Active Directory Users and Computers**, expand your domain, right-click the **Users** container, and then click **Properties**.</span></span>
    
3. <span data-ttu-id="21f16-107">Dans **Propriétés de CSAdministrator**, cliquez sur l’onglet **Membres**.</span><span class="sxs-lookup"><span data-stu-id="21f16-107">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
4. <span data-ttu-id="21f16-p101">Sous l’onglet Membres, cliquez sur **Ajouter**. Dans **Sélectionner des utilisateurs, des contacts, des ordinateurs, des comptes de service ou des groupes**, recherchez **Entrez les noms des objets à sélectionner**. Tapez le ou les noms d’utilisateur ou de groupe à ajouter au groupe CSAdministrators. Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="21f16-p101">On the Members tab, click **Add**. In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**. Type the user name(s) or group name(s) to add to the group CSAdministrators. Click **OK**.</span></span>
    
5. <span data-ttu-id="21f16-p102">Sous l’onglet Membre, confirmez que les utilisateurs ou les groupes que vous avez sélectionnés sont présents. Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="21f16-p102">On the Members tab, confirm that the users or groups that you selected are present. Click **OK**.</span></span>
    
> [!TIP]
> <span data-ttu-id="21f16-114">Le panneau de configuration Skype entreprise Server est un outil de contrôle d’accès basé sur un rôle.</span><span class="sxs-lookup"><span data-stu-id="21f16-114">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="21f16-115">L’appartenance au groupe CsAdministrator donne à un utilisateur qui utilise le panneau de configuration Skype entreprise Server le contrôle total pour toutes les fonctions de configuration disponibles.</span><span class="sxs-lookup"><span data-stu-id="21f16-115">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all the configuration functions available.</span></span> <span data-ttu-id="21f16-116">D’autres rôles conçus pour des fonctions spécifiques sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="21f16-116">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="21f16-117">Les utilisateurs n’ont pas besoin d’être activés pour Skype entreprise Server afin d’être membres des groupes de gestion.</span><span class="sxs-lookup"><span data-stu-id="21f16-117">Users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
<span data-ttu-id="21f16-118">Les autres rôles sont les suivants:</span><span class="sxs-lookup"><span data-stu-id="21f16-118">Other roles include:</span></span>
  
- <span data-ttu-id="21f16-119">**CsArchiving:** Les membres de ce groupe peuvent exécuter toutes les fonctions d’archivage, telles que la configuration et la gestion du rôle serveur d’archivage.</span><span class="sxs-lookup"><span data-stu-id="21f16-119">**CsArchiving:** Members of this group can perform all archiving functions, such as configuring and managing the Archiving Server role.</span></span>
    
- <span data-ttu-id="21f16-p104">**CsHelpDesk :** les membres de ce groupe peuvent afficher la configuration et le déploiement, y compris les propriétés et stratégies d’utilisateurs. Ils peuvent également effectuer des tâches de dépannage spécifiques.</span><span class="sxs-lookup"><span data-stu-id="21f16-p104">**CsHelpDesk:** Members of this group can view the configuration and deployment, including user properties and policies. Members can also perform specific troubleshooting tasks.</span></span>
    
- <span data-ttu-id="21f16-p105">**CsLocationAdministrator :** les membres de ce groupe disposent des droits d’utilisateur les moins élevés associés à la gestion du système Enhanced 9-1-1 (E9-1-1). Ils peuvent créer des identificateurs de réseau et des emplacements E9-1-1 et les associer dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="21f16-p105">**CsLocationAdministrator:** Members have the lowest level of user rights associated with Enhanced 9-1-1 (E9-1-1) management. They can create E9-1-1 locations and network identifiers and associate those in the deployment.</span></span>
    
- <span data-ttu-id="21f16-124">**CsResponseGroupAdministrator :** les membres peuvent gérer et configurer le service Response Group.</span><span class="sxs-lookup"><span data-stu-id="21f16-124">**CsResponseGroupAdministrator:** Members can manage and configure the Response Group service.</span></span>
    
- <span data-ttu-id="21f16-125">**CsServerAdministrator:** Les membres peuvent gérer, surveiller et dépanner tous les serveurs exécutant Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="21f16-125">**CsServerAdministrator:** Members can manage, monitor, and troubleshoot all servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="21f16-126">**CsUserAdministrator :** les membres de ce groupe peuvent gérer, activer et désactiver des utilisateurs et assigner des stratégies existantes aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="21f16-126">**CsUserAdministrator:** Members can manage, enable and disable users, and assign existing policies to users.</span></span>
    
- <span data-ttu-id="21f16-127">**CsViewOnlyAdministrator:** Les membres peuvent afficher le déploiement et la configuration des informations serveur.</span><span class="sxs-lookup"><span data-stu-id="21f16-127">**CsViewOnlyAdministrator:** Members can view the deployment and configuration of the server information.</span></span> <span data-ttu-id="21f16-128">Cette appartenance permet à un membre de surveiller l’état des serveurs exécutant Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="21f16-128">This membership enables a member to monitor the health of the servers running Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="21f16-129">**CsVoiceAdministrator:** Les membres peuvent créer, configurer et gérer les paramètres relatifs à la voix dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="21f16-129">**CsVoiceAdministrator:** Members can create, configure, and manage voice-related settings in Skype for Business Server.</span></span>
    
<span data-ttu-id="21f16-130">Pour garantir la sécurité et l’intégrité des contrôles d’accès basée sur les rôles, ajoutez des utilisateurs aux groupes qui déterminent le rôle que l’utilisateur effectue dans la gestion du déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="21f16-130">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span>
  

