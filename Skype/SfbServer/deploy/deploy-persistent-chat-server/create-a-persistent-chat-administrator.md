---
title: Création d’un administrateur de conversation permanente dans Skype Entreprise Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Résumé : Lisez cette rubrique pour savoir comment créer un rôle d’administrateur de serveur de conversation persistant pour activer la configuration initiale et la gestion des services de conversation permanents dans Skype pour Business Server 2015.'
ms.openlocfilehash: 4efe5dff2821784a24f51712b8a19dad83e47c3b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="aff20-103">Création d’un administrateur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="aff20-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="aff20-104">**Résumé :** Lisez cette rubrique pour savoir comment créer un rôle d’administrateur de serveur de conversation persistant pour activer la configuration initiale et la gestion des services de conversation permanents dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="aff20-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="aff20-105">Dans Skype pour Business Server, les utilisateurs effectuent des tâches spécifiques doivent être affectés en tant que membres d’un ou plusieurs des groupes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="aff20-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="aff20-106">Contrôle d’accès basée sur les rôles (RBAC) est utilisé pour accorder des privilèges en assignant des utilisateurs à Skype prédéfini pour les rôles d’administration de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="aff20-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="aff20-107">Ces rôles correspondent aux groupes de sécurité universels dans les Services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="aff20-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="aff20-108">Les membres du groupe de sécurité administrateur de Chat persistant, CsPersistentChatAdministrator, autorisés à accéder à des applets de commande serveur de Chat persistant, qui peut être exécutée via la Skype pour Business Server Management Shell ou le Skype pour entreprise Panneau de configuration de serveur.</span><span class="sxs-lookup"><span data-stu-id="aff20-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="aff20-109">Avant de configurer et d’administrer le serveur de conversations permanentes, assurez-vous que les autorisations et droits d’utilisateur ont été correctement définis, et que les utilisateurs possédant le rôle d’administrateur de conversation permanente sont ajoutés au groupe de sécurité Administrateur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="aff20-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="aff20-110">Créer un administrateur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="aff20-110">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="aff20-111">Pour ajouter un utilisateur au groupe de sécurité administrateur de Chat persistant, CsPersistentChatAdministrator, effectuez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="aff20-111">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="aff20-112">En utilisant un compte qui est autorisé à modifier l’appartenance à un groupe Active Directory, connectez-vous à l’ordinateur où Utilisateurs et ordinateurs Active Directory est installé.</span><span class="sxs-lookup"><span data-stu-id="aff20-112">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="aff20-113">Cliquez sur Démarrer, sur Tous les programmes, sur Outils d’administration, puis sur Utilisateurs et ordinateurs Active Directory.</span><span class="sxs-lookup"><span data-stu-id="aff20-113">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="aff20-114">Dans Utilisateurs et ordinateurs Active Directory, développez le nom de votre domaine et cliquez sur le conteneur Utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="aff20-114">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="aff20-115">Cliquez avec le bouton droit sur le groupe de sécurité CsPersistentChatAdministrator, puis cliquez sur Propriétés.</span><span class="sxs-lookup"><span data-stu-id="aff20-115">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="aff20-116">Dans la boîte de dialogue Propriétés, sous l’onglet Membres, cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="aff20-116">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="aff20-117">Dans la boîte de dialogue Sélectionner des utilisateurs, des ordinateurs, des contacts ou des groupes, tapez le nom d’utilisateur ou le nom d’affichage de l’utilisateur à ajouter au groupe dans la zone Entrer les noms des objets à sélectionner, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="aff20-117">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="aff20-118">Dans la boîte de dialogue Propriétés, cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="aff20-118">In the Properties dialog box, click OK.</span></span>
    

