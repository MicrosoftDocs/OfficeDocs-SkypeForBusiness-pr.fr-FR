---
title: Création d’un administrateur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Résumé: cette rubrique vous explique comment créer un rôle d’administrateur serveur de chat permanent permettant de configurer et de gérer les services de chat permanent dans Skype entreprise Server 2015.'
ms.openlocfilehash: 3692169a65d73c3951ce58e77b132a4f118c54e9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239766"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="7067b-103">Création d’un administrateur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="7067b-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7067b-104">**Résumé:** Pour plus d’informations sur la création d’un rôle d’administrateur de serveur de chat permanent, voir la rubrique Configuration initiale et gestion des services de chat permanent dans Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7067b-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7067b-105">Dans Skype entreprise Server, les utilisateurs qui effectuent des tâches spécifiques doivent être affectés en tant que membres d’un ou plusieurs groupes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="7067b-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="7067b-106">Le contrôle d’accès basé sur les rôles (RBAC) permet d’accorder des privilèges en attribuant aux utilisateurs des rôles d’administrateur prédéfinis Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="7067b-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="7067b-107">Ces rôles correspondent aux groupes de sécurité universelles dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7067b-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="7067b-108">Les membres du groupe de sécurité administrateur de chat permanent, CsPersistentChatAdministrator, ont accès aux cmdlets du serveur de chat permanent, qui peuvent être exécutées à l’aide de Skype entreprise Server Management Shell ou de Skype entreprise. Panneau de configuration du serveur.</span><span class="sxs-lookup"><span data-stu-id="7067b-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="7067b-109">Avant de configurer et d’administrer le serveur de conversations permanentes, assurez-vous que les autorisations et droits d’utilisateur ont été correctement définis, et que les utilisateurs possédant le rôle d’administrateur de conversation permanente sont ajoutés au groupe de sécurité Administrateur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="7067b-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="7067b-110">La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7067b-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="7067b-111">La même fonctionnalité est disponible dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7067b-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="7067b-112">Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="7067b-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="7067b-113">Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="7067b-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="7067b-114">Create a Persistent Chat administrator</span><span class="sxs-lookup"><span data-stu-id="7067b-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="7067b-115">Pour ajouter un utilisateur au groupe de sécurité administrateur de conversations permanentes, CsPersistentChatAdministrator, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="7067b-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="7067b-116">En utilisant un compte qui est autorisé à modifier l’appartenance à un groupe Active Directory, connectez-vous à l’ordinateur où Utilisateurs et ordinateurs Active Directory est installé.</span><span class="sxs-lookup"><span data-stu-id="7067b-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="7067b-117">Cliquez sur Démarrer, sur Tous les programmes, sur Outils d’administration, puis sur Utilisateurs et ordinateurs Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7067b-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="7067b-118">Dans Utilisateurs et ordinateurs Active Directory, développez le nom de votre domaine et cliquez sur le conteneur Utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="7067b-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="7067b-119">Cliquez avec le bouton droit sur le groupe de sécurité CsPersistentChatAdministrator, puis cliquez sur Propriétés.</span><span class="sxs-lookup"><span data-stu-id="7067b-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="7067b-120">Dans la boîte de dialogue Propriétés, sous l’onglet Membres, cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="7067b-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="7067b-121">Dans la boîte de dialogue Sélectionner des utilisateurs, des ordinateurs, des contacts ou des groupes, tapez le nom d’utilisateur ou le nom d’affichage de l’utilisateur à ajouter au groupe dans la zone Entrer les noms des objets à sélectionner, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7067b-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="7067b-122">Dans la boîte de dialogue Propriétés, cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="7067b-122">In the Properties dialog box, click OK.</span></span>
    

