---
title: Préparer un schéma
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Pour préparer le schéma pour les Services de domaine Active Directory, vous exécutez l’étape de préparation du schéma dans le Skype pour l’Assistant Déploiement Business Server. Cliquez sur Exécuter pour commencer la préparation du schéma.
ms.openlocfilehash: fc9981e5a6f298d4d7697b00cde2798dd0b859ef
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216142"
---
# <a name="prepare-schema"></a><span data-ttu-id="406a7-104">Préparer un schéma</span><span class="sxs-lookup"><span data-stu-id="406a7-104">Prepare Schema</span></span>
 
<span data-ttu-id="406a7-105">Pour préparer le schéma pour les Services de domaine Active Directory, vous exécutez l’étape de préparation du schéma dans le Skype pour l’Assistant Déploiement Business Server.</span><span class="sxs-lookup"><span data-stu-id="406a7-105">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="406a7-106">Cliquez sur **Exécuter** pour commencer la préparation du schéma.</span><span class="sxs-lookup"><span data-stu-id="406a7-106">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="406a7-107">L’étape de préparation du schéma lit le schéma fourni fichiers définition dans le \Program Files\Skype pour Business Server 2019\Deployment\Setup répertoire sur le système de l’Assistant déploiement est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="406a7-107">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Skype for Business Server 2019\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="406a7-108">Ces fichiers sont également disponibles sur le support d’installation, dans le répertoire \Support\Schema.</span><span class="sxs-lookup"><span data-stu-id="406a7-108">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="406a7-109">L’étape Préparer un schéma développera le schéma et rapportera le statut du processus.</span><span class="sxs-lookup"><span data-stu-id="406a7-109">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="406a7-110">Elle vous notifiera également l’achèvement du processus.</span><span class="sxs-lookup"><span data-stu-id="406a7-110">It will also notify you when the process is complete.</span></span> <span data-ttu-id="406a7-111">L’écran de résumé vous permettra d’afficher les journaux du processus.</span><span class="sxs-lookup"><span data-stu-id="406a7-111">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="406a7-112">Passez en revue les journaux pour vous assurer que la préparation est terminée et qu’elle a abouti.</span><span class="sxs-lookup"><span data-stu-id="406a7-112">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="406a7-113">Pour étendre le schéma, vous devez être connecté au domaine en tant que membre du groupe Administrateurs du schéma et du groupe Administrateurs d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="406a7-113">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="406a7-114">Classes et attributs sont ajoutés pour étendre le schéma Active Directory Domain Services pour prendre en charge Skype pour Business Server server service et les objets utilisateur.</span><span class="sxs-lookup"><span data-stu-id="406a7-114">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server server, service, and user objects.</span></span> <span data-ttu-id="406a7-115">Avant d’étendre le schéma, effectuez une sauvegarde de l’état du système du contrôleur de domaine qui contient le rôle de contrôleur de schéma.</span><span class="sxs-lookup"><span data-stu-id="406a7-115">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="406a7-116">Cette opération est irréversible.</span><span class="sxs-lookup"><span data-stu-id="406a7-116">Extending the schema is not reversible.</span></span> <span data-ttu-id="406a7-117">Vous devez faire tout votre possible pour limiter l’impact potentiel d’un échec de l’extension du schéma et pour garantir la réussite de l’extension du schéma.</span><span class="sxs-lookup"><span data-stu-id="406a7-117">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="406a7-118">Ceci est particulièrement important en cas de perte de communication ou de toute autre défaillance côté serveur.</span><span class="sxs-lookup"><span data-stu-id="406a7-118">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="406a7-119">Vous devez effectuer une sauvegarde du contrôleur de domaine maître de schéma et une sauvegarde complète d’Active Directory.</span><span class="sxs-lookup"><span data-stu-id="406a7-119">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="406a7-120">Pour effectuer une sauvegarde du contrôleur de domaine maître de schéma et une sauvegarde complète d’Active Directory :</span><span class="sxs-lookup"><span data-stu-id="406a7-120">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="406a7-121">Déconnectez du réseau le contrôleur de domaine qui contient le rôle de contrôleur de schéma.</span><span class="sxs-lookup"><span data-stu-id="406a7-121">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="406a7-122">Effectuez une sauvegarde de l’état du système du contrôleur de domaine qui contient le contrôleur de schéma.</span><span class="sxs-lookup"><span data-stu-id="406a7-122">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="406a7-123">Étendez le schéma.</span><span class="sxs-lookup"><span data-stu-id="406a7-123">Extend the schema.</span></span>
    
4. <span data-ttu-id="406a7-124">Lorsque l’extension aboutit, reconnectez le contrôleur de domaine au réseau et assurez-vous que la réplication est active et qu’elle fonctionne.</span><span class="sxs-lookup"><span data-stu-id="406a7-124">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="406a7-125">Dans le cas improbable d’un échec, restaurez l’état système du contrôleur de domaine et Active Directory à l’aide de la sauvegarde de l’état du système que vous avez effectuée précédemment.</span><span class="sxs-lookup"><span data-stu-id="406a7-125">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="406a7-126">Si vous avez besoin passer en revue les fichiers journaux qui sont créés par le Skype pour l’Assistant de déploiement Business Server, vous trouverez les fichiers sur l’ordinateur où a été exécuté l’Assistant déploiement, dans le répertoire des utilisateurs de l’utilisateur Active Directory qui a exécuté l’étape.</span><span class="sxs-lookup"><span data-stu-id="406a7-126">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="406a7-127">Par exemple, si l’utilisateur est connecté en tant qu’administrateur de domaine dans le domaine Contoso.net, les fichiers journaux se trouvent dans : C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="406a7-127">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

