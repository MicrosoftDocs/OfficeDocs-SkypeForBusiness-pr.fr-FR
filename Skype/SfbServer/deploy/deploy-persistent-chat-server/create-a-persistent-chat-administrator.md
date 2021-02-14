---
title: Créer un administrateur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Résumé : Lisez cette rubrique pour découvrir comment créer un rôle d’administrateur de serveur de conversation permanente pour activer la configuration initiale et la gestion des services de conversation permanente dans Skype Entreprise Server 2015.'
ms.openlocfilehash: eea989b0284353e193ebf99a0be99b2d0811e532
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802094"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a><span data-ttu-id="07557-103">Créer un administrateur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="07557-103">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="07557-104">**Résumé :** Lisez cette rubrique pour découvrir comment créer un rôle d’administrateur de serveur de conversation permanente pour activer la configuration initiale et la gestion des services de conversation permanente dans Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="07557-104">**Summary:** Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="07557-105">Dans Skype Entreprise Server, les utilisateurs qui effectuent des tâches spécifiques doivent être affectés en tant que membres d’un ou plusieurs groupes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="07557-105">In Skype for Business Server, users who perform specific tasks must be assigned as members of one or more specific groups.</span></span> <span data-ttu-id="07557-106">Role-Based contrôle d’accès (RBAC) est utilisé pour accorder des privilèges en attribuant des utilisateurs à des rôles d’administration Skype Entreprise Server prédéfincis.</span><span class="sxs-lookup"><span data-stu-id="07557-106">Role-Based Access Control (RBAC) is used to grant privileges by assigning users to predefined Skype for Business Server administrative roles.</span></span> <span data-ttu-id="07557-107">Ces rôles correspondent aux groupes de sécurité universels dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="07557-107">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="07557-108">Les membres du groupe de sécurité Administrateur de conversation permanente, CsPersistentChatAdministrator, ont accès aux cmdlets du serveur de conversation permanente, qui peuvent être exécutées à l’aide de Skype Entreprise Server Management Shell ou du Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="07557-108">Members of the Persistent Chat Administrator security group, CsPersistentChatAdministrator, are granted access to the Persistent Chat Server cmdlets, which can be executed using either the Skype for Business Server Management Shell or the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="07557-109">Avant de configurer et d’administrer le serveur de conversation permanente, assurez-vous que les droits et autorisations utilisateur appropriés sont en place et que tous les utilisateurs qui agiraient en tant qu’administrateurs de conversation permanente sont ajoutés au groupe de sécurité Administrateur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="07557-109">Before configuring and administering Persistent Chat Server, be sure that the appropriate user rights and permissions are in place, and that any users who will act as Persistent Chat administrators are added to the Persistent Chat Administrator security group.</span></span>
  
> [!NOTE] 
> <span data-ttu-id="07557-110">La conversation permanente est disponible dans Skype Entreprise Server 2015, mais n’est plus prise en charge dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="07557-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="07557-111">La même fonctionnalité est disponible dans Teams.</span><span class="sxs-lookup"><span data-stu-id="07557-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="07557-112">Pour plus d’informations, voir [La mise à niveau de Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="07557-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="07557-113">Si vous devez utiliser la conversation permanente, vous pouvez migrer les utilisateurs nécessitant cette fonctionnalité vers Teams ou continuer à utiliser Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="07557-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="create-a-persistent-chat-administrator"></a><span data-ttu-id="07557-114">Créer un administrateur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="07557-114">Create a Persistent Chat administrator</span></span>

<span data-ttu-id="07557-115">Pour ajouter un utilisateur au groupe de sécurité Administrateur de conversation permanente, CsPersistentChatAdministrator, effectuez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="07557-115">To add a user to the Persistent Chat Administrator security group, CsPersistentChatAdministrator, perform the following steps:</span></span>
  
1. <span data-ttu-id="07557-116">À l’aide d’un compte autorisé à modifier l’appartenance à un groupe Active Directory, connectez-vous à un ordinateur sur lequel utilisateurs et ordinateurs Active Directory ont été installés.</span><span class="sxs-lookup"><span data-stu-id="07557-116">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers have been installed.</span></span>
    
2. <span data-ttu-id="07557-117">Cliquez sur Démarrer, sur Tous les programmes, sur Outils d’administration, puis sur Utilisateurs et ordinateurs Active Directory.</span><span class="sxs-lookup"><span data-stu-id="07557-117">Click Start, click All Programs, click Administrative Tools, and then click Active Directory Users and Computers.</span></span>
    
3. <span data-ttu-id="07557-118">Dans Utilisateurs et ordinateurs Active Directory, développez le nom de votre domaine et cliquez sur le conteneur Utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="07557-118">In Active Directory Users and Computers, expand the name of your domain and click the Users container.</span></span>
    
4. <span data-ttu-id="07557-119">Cliquez avec le bouton droit sur le groupe de sécurité CsPersistentChatAdministrator, puis cliquez sur Propriétés.</span><span class="sxs-lookup"><span data-stu-id="07557-119">Right-click the security group CsPersistentChatAdministrator, and then click Properties.</span></span>
    
5. <span data-ttu-id="07557-120">Dans la boîte de dialogue Propriétés, sous l’onglet Membres, cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="07557-120">In the Properties dialog box, on the Members tab, click Add.</span></span>
    
6. <span data-ttu-id="07557-121">Dans la boîte de dialogue Sélectionner des utilisateurs, des ordinateurs, des contacts ou des groupes, tapez le nom d’utilisateur ou le nom complet de l’utilisateur à ajouter au groupe dans la zone Entrez les noms des objets à sélectionner, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="07557-121">In the Select Users, Computers, Contact, or Groups dialog box, type the user name or display name of the user to be added to the group in the Enter the object names to select box and then click OK.</span></span>
    
7. <span data-ttu-id="07557-122">Dans la boîte de dialogue Propriétés, cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="07557-122">In the Properties dialog box, click OK.</span></span>
    

