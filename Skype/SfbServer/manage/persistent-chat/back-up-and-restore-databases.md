---
title: Back up and restore Persistent Chat databases in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Résumé : Découvrez comment restaurer des bases de données de serveur de conversation permanente dans Skype Entreprise Server 2015.'
ms.openlocfilehash: 2c99f5e955756020f68b51ea214858c23fee0a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826374"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="49288-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="49288-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="49288-104">**Résumé :** Découvrez comment back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="49288-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="49288-105">Le serveur de conversation permanente SQL Server un logiciel de base de données pour stocker les données de salle de conversation, telles que l’historique et le contenu, la configuration, la mise en service des utilisateurs et d’autres métadonnées pertinentes.</span><span class="sxs-lookup"><span data-stu-id="49288-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="49288-106">En outre, si votre organisation a des réglementations qui exigent l’archivage de l’activité de conversation permanente et que le service de conformité facultatif est activé, le logiciel de base de données SQL Server est utilisé pour stocker les données de conformité, y compris le contenu et les événements de conversation, tels que la jointation et la sortie de salles.</span><span class="sxs-lookup"><span data-stu-id="49288-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="49288-107">Le contenu de la salle de conversation est stocké dans la base de données de conversation permanente (mgc).</span><span class="sxs-lookup"><span data-stu-id="49288-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="49288-108">Les données de conformité sont stockées dans la base de données de conformité (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="49288-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="49288-109">Il s’agit de données critiques qui doivent être régulièrement backed.</span><span class="sxs-lookup"><span data-stu-id="49288-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="49288-110">La conversation permanente est disponible dans Skype Entreprise Server 2015, mais n’est plus prise en charge dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="49288-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="49288-111">La même fonctionnalité est disponible dans Teams.</span><span class="sxs-lookup"><span data-stu-id="49288-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="49288-112">Pour plus d’informations, voir [La mise à niveau de Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="49288-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="49288-113">Si vous devez utiliser la conversation permanente, vous pouvez migrer les utilisateurs nécessitant cette fonctionnalité vers Teams ou continuer à utiliser Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="49288-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="49288-114">Back up the databases</span><span class="sxs-lookup"><span data-stu-id="49288-114">Back up the databases</span></span>

<span data-ttu-id="49288-115">Il existe deux façons de la backing up Persistent Chat data.</span><span class="sxs-lookup"><span data-stu-id="49288-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="49288-116">SQL Server sauvegarde</span><span class="sxs-lookup"><span data-stu-id="49288-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="49288-117">**L’cmdlet Export-CsPersistentChatData,** qui exporte les données de conversation permanente en tant que fichier</span><span class="sxs-lookup"><span data-stu-id="49288-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="49288-118">Les données créées à l’aide de la sauvegarde SQL Server nécessitent beaucoup plus d’espace disque (20 fois plus éventuellement) que celles créées par **l';export-CsPersistentChatData,** mais la sauvegarde SQL Server est probablement une procédure que vous connaissez déjà.</span><span class="sxs-lookup"><span data-stu-id="49288-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="49288-119">Si vous souhaitez utiliser des procédures SQL Server de sauvegarde, consultez votre documentation SQL pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="49288-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="49288-120">Si vous souhaitez utiliser l’cmdlet **Export-CsPersistentChatData,** vous pouvez spécifier la commande comme suit :</span><span class="sxs-lookup"><span data-stu-id="49288-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="49288-121">ou</span><span class="sxs-lookup"><span data-stu-id="49288-121">or</span></span>
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="49288-122">Par exemple, la commande suivante exporte les données de conversation permanente à partir de la base de données de conversation permanente située sur le serveur atl-sql-001.contoso.com ; les données exportées sont stockées dans le fichier C:\Logs\PersistentChatData.zip.</span><span class="sxs-lookup"><span data-stu-id="49288-122">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip.</span></span> <span data-ttu-id="49288-123">Étant donné que le paramètre Level n’a pas été spécifié, la commande exporte entièrement les informations de conversation permanente :</span><span class="sxs-lookup"><span data-stu-id="49288-123">Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="49288-124">Restaurer les bases de données</span><span class="sxs-lookup"><span data-stu-id="49288-124">Restore the databases</span></span>

<span data-ttu-id="49288-125">La façon dont vous restituer vos données de conversation permanente dépend de la méthode que vous avez utilisée pour les restaurer.</span><span class="sxs-lookup"><span data-stu-id="49288-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="49288-126">Si vous avez utilisé SQL Server procédures de sauvegarde, vous devez utiliser SQL Server de restauration automatique.</span><span class="sxs-lookup"><span data-stu-id="49288-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="49288-127">Si vous avez utilisé l’cmdlet **Export-CsPersistentChatData** pour la protection des données de conversation permanente, vous devez utiliser l’cmdlet **Import-CsPersistentChatData** pour restaurer les données :</span><span class="sxs-lookup"><span data-stu-id="49288-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="49288-128">ou</span><span class="sxs-lookup"><span data-stu-id="49288-128">or</span></span>
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
