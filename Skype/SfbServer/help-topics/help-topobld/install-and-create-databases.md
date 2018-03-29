---
title: Installer et créer des bases de données
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: Vous sélectionnez les bases de données que vous souhaitez créer pour votre déploiement. Par défaut, la base de données sera créé sur le SQL Server définis dans un site défini et sera automatiquement déployer et configurer les fichiers de base de données basées sur le SQL Server que vous placez sur les bases de données.
ms.openlocfilehash: cf838e66dc5e9592ba71dd9d44fa5fc333c6dbc7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="install-and-create-databases"></a><span data-ttu-id="3e861-104">Installer et créer des bases de données</span><span class="sxs-lookup"><span data-stu-id="3e861-104">Install and Create Databases</span></span>
 
<span data-ttu-id="3e861-105">Vous sélectionnez les bases de données que vous souhaitez créer pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="3e861-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="3e861-106">Par défaut, la base de données sera créé sur le SQL Server définis dans un site défini et sera automatiquement déployer et configurer les fichiers de base de données basées sur le SQL Server que vous placez sur les bases de données.</span><span class="sxs-lookup"><span data-stu-id="3e861-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>
  
 <span data-ttu-id="3e861-107">**Sélectionnez les bases de données que vous voulez créer**: cochez la case correspondant à des bases de données que vous souhaitez déployer et à configurer.</span><span class="sxs-lookup"><span data-stu-id="3e861-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="3e861-108">Activez la case à cocher de certaines ou toutes les bases de données que vous déploierez.</span><span class="sxs-lookup"><span data-stu-id="3e861-108">Select the check box of any or all databases that you will deploy.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="3e861-109">Le SQL Server doit déjà être configurée pour l’instance (le cas échéant) et les ports de pare-feu doivent être ouverts pour tenir compte de l’instance que vous déployez les bases de données.</span><span class="sxs-lookup"><span data-stu-id="3e861-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="3e861-110">Pour plus d’informations, consultez [Configuration de SQL Server de Lync Server 2013 Preview](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="3e861-110">For details, see [Configure SQL Server for Lync Server 2013 Preview](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>
  
 <span data-ttu-id="3e861-111">**Avancé**: cliquez sur le SQL Server et cliquez sur le bouton **Avancé** pour sélectionner les options de la base de données des emplacements de fichiers sur votre SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3e861-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="3e861-112">Pour plus d’informations sur le placement des fichiers de base de données avancées, consultez la [Base de données Installation à l’aide de Communications Server Management Shell](http://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="3e861-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](http://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>
  
 <span data-ttu-id="3e861-113">**Sauvegarder**: cliquez sur ce bouton pour revenir à l’écran précédent (ne peut pas toujours être disponible, selon la façon dont vous êtes arrivés à cette boîte de dialogue).</span><span class="sxs-lookup"><span data-stu-id="3e861-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>
  
 <span data-ttu-id="3e861-114">**Suivant**: cliquez sur ce bouton valide votre sélection dans la boîte de dialogue en cours et permet d’accéder à la boîte de dialogue suivante pour configurer des informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="3e861-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>
  
 <span data-ttu-id="3e861-115">**Annuler**: cliquez sur ce bouton va quitter la configuration et ignorer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="3e861-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="3e861-116">Certains, mais pas tous les écrans de configuration vous demandera si vous souhaitez ignorer vos modifications et de quitter.</span><span class="sxs-lookup"><span data-stu-id="3e861-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="3e861-117">Si vous sélectionnez **Oui** ferme la configuration en cours et fermer la configuration actuelle et revenir au Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="3e861-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="3e861-118">Si vous sélectionnez **non** pour revenir à la boîte de dialogue de configuration en cours et vous permet de continuer la configuration.</span><span class="sxs-lookup"><span data-stu-id="3e861-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>
  
 <span data-ttu-id="3e861-119">**Aide**: cliquer sur le bouton **aide** affiche ces informations d’aide associées à la boîte de dialogue de configuration en cours.</span><span class="sxs-lookup"><span data-stu-id="3e861-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>
  

