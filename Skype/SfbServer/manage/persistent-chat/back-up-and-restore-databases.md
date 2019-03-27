---
title: Sauvegarde et restauration des bases de données de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Résumé : Découvrez comment sauvegarder et restaurer des bases de données de serveur de conversation permanente dans Skype pour Business Server 2015.'
ms.openlocfilehash: a07321c7e9167e830a7af472e9022b669a45c3e7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886422"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="91e93-103">Sauvegarde et restauration des bases de données de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="91e93-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="91e93-104">**Résumé :** Découvrez comment sauvegarder et restaurer des bases de données de serveur de conversation permanente dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="91e93-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="91e93-105">Persistent Chat Server requiert le logiciel de base de données SQL Server pour stocker les données de salle de conversation, telles que l’historique de contenu, configuration, mise en service de l’utilisateur et autres métadonnées appropriées.</span><span class="sxs-lookup"><span data-stu-id="91e93-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="91e93-106">En outre, si votre organisation dispose d’une réglementation qui nécessitent l’activité de conversation permanente à archiver, et le service de conformité facultatif est activé, le logiciel de base de données SQL Server est utilisé pour stocker les données de conformité, y compris le contenu de conversation et les événements, tels que entrée et de sortie des salles.</span><span class="sxs-lookup"><span data-stu-id="91e93-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="91e93-107">Contenu de la salle de conversation est stocké dans la base de données conversation permanente (mgc).</span><span class="sxs-lookup"><span data-stu-id="91e93-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="91e93-108">Les données de conformité sont conservées dans la base de données de conformité (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="91e93-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="91e93-109">Il s’agit de données vitales qui doivent être sauvegardées régulièrement.</span><span class="sxs-lookup"><span data-stu-id="91e93-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="91e93-110">Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="91e93-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="91e93-111">La même fonctionnalité est disponible dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="91e93-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="91e93-112">Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="91e93-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="91e93-113">Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="91e93-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="91e93-114">Sauvegarde des bases de données</span><span class="sxs-lookup"><span data-stu-id="91e93-114">Back up the databases</span></span>

<span data-ttu-id="91e93-115">Il existe deux façons de sauvegarde des données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="91e93-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="91e93-116">Sauvegarde SQL Server</span><span class="sxs-lookup"><span data-stu-id="91e93-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="91e93-117">L’applet de commande **Export-CsPersistentChatData** , qui exporte les données de conversation permanente en tant que fichier</span><span class="sxs-lookup"><span data-stu-id="91e93-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="91e93-118">Les données créées à l’aide de la sauvegarde SQL Server nécessitent beaucoup plus d’espace disque (jusqu’à 20 fois plus) que celles créées par l’applet de commande **Export-CsPersistentChatData**, mais la sauvegarde SQL Server est sans doute une procédure plus familière.</span><span class="sxs-lookup"><span data-stu-id="91e93-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="91e93-119">Si vous souhaitez utiliser les procédures de sauvegarde SQL Server, reportez-vous à votre documentation SQL pour en savoir plus.</span><span class="sxs-lookup"><span data-stu-id="91e93-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="91e93-120">Si vous souhaitez utiliser l’applet de commande **Export-CsPersistentChatData**, vous pouvez préciser la commande comme suit :</span><span class="sxs-lookup"><span data-stu-id="91e93-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="91e93-121">ou</span><span class="sxs-lookup"><span data-stu-id="91e93-121">or</span></span>
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="91e93-p103">Par exemple, la commande suivante exporte les données de conversation permanente de la base de données de conversation permanente située sur le serveur atl-sql-001.contoso.com ; les données exportées seront stockées dans le fichier C:\Logs\PersistentChatData.zip. Dans la mesure où le paramètre Level n’est pas spécifié, la commande exportera l’intégralité des informations de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="91e93-p103">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip. Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="91e93-124">Restauration des bases de données</span><span class="sxs-lookup"><span data-stu-id="91e93-124">Restore the databases</span></span>

<span data-ttu-id="91e93-125">Comment restaurer vos données de conversation permanente dépend de la méthode qui vous permet de sauvegarder.</span><span class="sxs-lookup"><span data-stu-id="91e93-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="91e93-126">Si vous avez utilisé des procédures de sauvegarde SQL Server, vous devez utiliser des procédures de restauration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="91e93-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="91e93-127">Si vous avez utilisé l’applet de commande **Export-CsPersistentChatData** pour sauvegarder les données de conversation permanente, vous devez utiliser la cmdlet **Import-CsPersistentChatData** pour restaurer les données :</span><span class="sxs-lookup"><span data-stu-id="91e93-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="91e93-128">ou</span><span class="sxs-lookup"><span data-stu-id="91e93-128">or</span></span>
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
