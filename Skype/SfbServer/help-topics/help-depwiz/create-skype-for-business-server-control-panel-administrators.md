---
title: Créer des administrateurs du Panneau de configuration Skype Entreprise Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: 'Pour accorder l’accès à la Skype pour Business Server 2015, effectuez les opérations suivantes :'
ms.openlocfilehash: db781611e2df2abf23c071673d3dfe0570f5700b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a><span data-ttu-id="ee7f8-103">Créer des administrateurs du Panneau de configuration Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ee7f8-103">Create Skype for Business Server Control Panel Administrators</span></span>
 
<span data-ttu-id="ee7f8-104">Pour accorder l’accès à la Skype pour Business Server 2015, effectuez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ee7f8-104">To grant access to the Skype for Business Server 2015, do the following:</span></span>
  
1. <span data-ttu-id="ee7f8-105">Ouvrez une session en tant que membre du groupe Administrateurs du domaine ou du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ee7f8-105">Log on as a member of the Domain Admins group or the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="ee7f8-106">Ouvrez **Utilisateurs et ordinateurs Active Directory**, développez votre domaine, cliquez avec le bouton droit sur le conteneur **Utilisateurs**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ee7f8-106">Open **Active Directory Users and Computers**, expand your domain, right-click the **Users** container, and then click **Properties**.</span></span>
    
3. <span data-ttu-id="ee7f8-107">Dans **Propriétés de CSAdministrator**, cliquez sur l’onglet **Membres**.</span><span class="sxs-lookup"><span data-stu-id="ee7f8-107">In **CSAdministrator Properties**, click the **Members** tab.</span></span>
    
4. <span data-ttu-id="ee7f8-p101">Sous l’onglet Membres, cliquez sur **Ajouter**. Dans **Sélectionner des utilisateurs, des contacts, des ordinateurs, des comptes de service ou des groupes**, recherchez **Entrez les noms des objets à sélectionner**. Tapez le ou les noms d’utilisateur ou de groupe à ajouter au groupe CSAdministrators. Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ee7f8-p101">On the Members tab, click **Add**. In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**. Type the user name(s) or group name(s) to add to the group CSAdministrators. Click **OK**.</span></span>
    
5. <span data-ttu-id="ee7f8-p102">Sous l’onglet Membre, confirmez que les utilisateurs ou les groupes que vous avez sélectionnés sont présents. Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ee7f8-p102">On the Members tab, confirm that the users or groups that you selected are present. Click **OK**.</span></span>
    
> [!TIP]
> <span data-ttu-id="ee7f8-114">Le Skype pour le panneau de configuration de Business Server est un outil de contrôle d’accès basé sur les rôles.</span><span class="sxs-lookup"><span data-stu-id="ee7f8-114">The Skype for Business Server Control Panel is a role-based access control tool.</span></span> <span data-ttu-id="ee7f8-115">Appartenance au groupe CsAdministrator donne à l’utilisateur qui utilise le Skype pour le panneau de configuration de Business Server un contrôle total sur toutes les fonctions de configuration disponibles.</span><span class="sxs-lookup"><span data-stu-id="ee7f8-115">Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all the configuration functions available.</span></span> <span data-ttu-id="ee7f8-116">Il existe d’autres rôles disponibles conçus pour des fonctions spécifiques.</span><span class="sxs-lookup"><span data-stu-id="ee7f8-116">There are other roles available that are designed for specific functions.</span></span> <span data-ttu-id="ee7f8-117">Les utilisateurs n’ont pas à activer pour Skype pour Business Server afin de devenir membres des groupes d’administration.</span><span class="sxs-lookup"><span data-stu-id="ee7f8-117">Users do not have to be enabled for Skype for Business Server in order to be made members of the management groups.</span></span> 
  
<span data-ttu-id="ee7f8-118">Autres rôles sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="ee7f8-118">Other roles include:</span></span>
  
- <span data-ttu-id="ee7f8-119">**CsArchiving :** Les membres de ce groupe peuvent effectuer toutes les fonctions d’archivage, tels que la configuration et la gestion du rôle de serveur d’archivage.</span><span class="sxs-lookup"><span data-stu-id="ee7f8-119">**CsArchiving:** Members of this group can perform all archiving functions, such as configuring and managing the Archiving Server role.</span></span>
    
- <span data-ttu-id="ee7f8-p104">**CsHelpDesk :** les membres de ce groupe peuvent afficher la configuration et le déploiement, y compris les propriétés et stratégies d’utilisateurs. Ils peuvent également effectuer des tâches de dépannage spécifiques.</span><span class="sxs-lookup"><span data-stu-id="ee7f8-p104">**CsHelpDesk:** Members of this group can view the configuration and deployment, including user properties and policies. Members can also perform specific troubleshooting tasks.</span></span>
    
- <span data-ttu-id="ee7f8-p105">**CsLocationAdministrator :** les membres de ce groupe disposent des droits d’utilisateur les moins élevés associés à la gestion du système Enhanced 9-1-1 (E9-1-1). Ils peuvent créer des identificateurs de réseau et des emplacements E9-1-1 et les associer dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="ee7f8-p105">**CsLocationAdministrator:** Members have the lowest level of user rights associated with Enhanced 9-1-1 (E9-1-1) management. They can create E9-1-1 locations and network identifiers and associate those in the deployment.</span></span>
    
- <span data-ttu-id="ee7f8-124">**CsResponseGroupAdministrator :** les membres peuvent gérer et configurer le service Response Group.</span><span class="sxs-lookup"><span data-stu-id="ee7f8-124">**CsResponseGroupAdministrator:** Members can manage and configure the Response Group service.</span></span>
    
- <span data-ttu-id="ee7f8-125">**CsServerAdministrator :** Les membres peuvent gérer, contrôler et résoudre les problèmes de tous les serveurs exécutant Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="ee7f8-125">**CsServerAdministrator:** Members can manage, monitor, and troubleshoot all servers running Skype for Business Server.</span></span>
    
- <span data-ttu-id="ee7f8-126">**CsUserAdministrator :** les membres de ce groupe peuvent gérer, activer et désactiver des utilisateurs et assigner des stratégies existantes aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ee7f8-126">**CsUserAdministrator:** Members can manage, enable and disable users, and assign existing policies to users.</span></span>
    
- <span data-ttu-id="ee7f8-127">**CsViewOnlyAdministrator :** Les membres peuvent afficher le déploiement et la configuration des informations serveur.</span><span class="sxs-lookup"><span data-stu-id="ee7f8-127">**CsViewOnlyAdministrator:** Members can view the deployment and configuration of the server information.</span></span> <span data-ttu-id="ee7f8-128">Cet abonnement permet à un membre surveiller la santé des serveurs Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ee7f8-128">This membership enables a member to monitor the health of the servers running Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="ee7f8-129">**CsVoiceAdministrator :** Les membres peuvent créer, configurer et gérer les paramètres liés à la voix dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="ee7f8-129">**CsVoiceAdministrator:** Members can create, configure, and manage voice-related settings in Skype for Business Server.</span></span>
    
<span data-ttu-id="ee7f8-130">Pour vous aider à assurer la sécurité et intégrité de contrôle d’accès basé sur des rôles, ajouter des utilisateurs aux groupes qui définissent quel rôle de l’utilisateur dans la gestion de la Skype pour le déploiement du serveur de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="ee7f8-130">To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment.</span></span>
  

