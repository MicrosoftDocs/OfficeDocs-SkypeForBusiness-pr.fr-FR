---
title: Sauvegarde et restauration des bases de données de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 'Résumé: Découvrez comment sauvegarder et restaurer des bases de données serveur de chat permanent dans Skype entreprise Server 2015.'
ms.openlocfilehash: 07d904620bbc5925ec6457924af6ee1e48d98d55
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279360"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="59a24-103">Sauvegarde et restauration des bases de données de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="59a24-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="59a24-104">**Résumé:** Découvrez comment sauvegarder et restaurer des bases de données serveur de chat permanent dans Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="59a24-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="59a24-105">Le serveur Chat permanent nécessite le logiciel de base de données SQL Server pour stocker des données de salle de conversation, telles que l’historique, le contenu, la configuration, la mise en service des utilisateurs et d’autres métadonnées pertinentes.</span><span class="sxs-lookup"><span data-stu-id="59a24-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="59a24-106">De plus, si votre organisation a des réglementations qui nécessitent l’archivage de l’activité de conversation permanente et que le service de conformité facultatif est activé, le logiciel de base de données SQL Server est utilisé pour stocker les données de conformité, y compris le contenu et les événements de conversation, comme salle de réunion et de départ.</span><span class="sxs-lookup"><span data-stu-id="59a24-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="59a24-107">Le contenu d’une salle de conversation est stocké dans la base de données de chat permanent (MGC).</span><span class="sxs-lookup"><span data-stu-id="59a24-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="59a24-108">Les données de conformité sont conservées dans la base de données de conformité (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="59a24-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="59a24-109">Il s’agit de données vitales qui doivent être sauvegardées régulièrement.</span><span class="sxs-lookup"><span data-stu-id="59a24-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="59a24-110">La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="59a24-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="59a24-111">La même fonctionnalité est disponible dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="59a24-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="59a24-112">Pour plus d’informations, reportez-vous à la rubrique [voyage de Skype entreprise à Microsoft teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="59a24-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="59a24-113">Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="59a24-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="59a24-114">Sauvegarde des bases de données</span><span class="sxs-lookup"><span data-stu-id="59a24-114">Back up the databases</span></span>

<span data-ttu-id="59a24-115">Il existe deux méthodes pour sauvegarder les données de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="59a24-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="59a24-116">Sauvegarde SQL Server</span><span class="sxs-lookup"><span data-stu-id="59a24-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="59a24-117">L’applet de passe **Export-CsPersistentChatData** , qui exporte les données de chat permanent en tant que fichier</span><span class="sxs-lookup"><span data-stu-id="59a24-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="59a24-118">Les données créées à l’aide de la sauvegarde SQL Server nécessitent beaucoup plus d’espace disque (jusqu’à 20 fois plus) que celles créées par l’applet de commande **Export-CsPersistentChatData**, mais la sauvegarde SQL Server est sans doute une procédure plus familière.</span><span class="sxs-lookup"><span data-stu-id="59a24-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="59a24-119">Si vous souhaitez utiliser les procédures de sauvegarde SQL Server, reportez-vous à votre documentation SQL pour en savoir plus.</span><span class="sxs-lookup"><span data-stu-id="59a24-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="59a24-120">Si vous souhaitez utiliser l’applet de commande **Export-CsPersistentChatData**, vous pouvez préciser la commande comme suit :</span><span class="sxs-lookup"><span data-stu-id="59a24-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="59a24-121">ou</span><span class="sxs-lookup"><span data-stu-id="59a24-121">or</span></span>
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="59a24-p103">Par exemple, la commande suivante exporte les données de conversation permanente de la base de données de conversation permanente située sur le serveur atl-sql-001.contoso.com ; les données exportées seront stockées dans le fichier C:\Logs\PersistentChatData.zip. Dans la mesure où le paramètre Level n’est pas spécifié, la commande exportera l’intégralité des informations de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="59a24-p103">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip. Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="59a24-124">Restauration des bases de données</span><span class="sxs-lookup"><span data-stu-id="59a24-124">Restore the databases</span></span>

<span data-ttu-id="59a24-125">Le mode de restauration des données de conversation persistante dépend de la méthode que vous avez utilisée pour les sauvegarder.</span><span class="sxs-lookup"><span data-stu-id="59a24-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="59a24-126">Si vous avez utilisé des procédures de sauvegarde SQL Server, vous devez utiliser des procédures de restauration SQL Server.</span><span class="sxs-lookup"><span data-stu-id="59a24-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="59a24-127">Si vous avez utilisé l’applet de cmdlet **Export-CsPersistentChatData** pour sauvegarder les données de conversation permanente, vous devez utiliser l’applet de passe **Import-CsPersistentChatData** pour restaurer les données:</span><span class="sxs-lookup"><span data-stu-id="59a24-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="59a24-128">ou</span><span class="sxs-lookup"><span data-stu-id="59a24-128">or</span></span>
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
