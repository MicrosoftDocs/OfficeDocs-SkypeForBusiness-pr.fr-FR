---
title: Installer et créer des bases de données
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: Vous sélectionnez les bases de données que vous voulez créer pour votre déploiement. Par défaut, la base de données est créée sur le serveur SQL Server défini dans le site défini et déploie et configure automatiquement les fichiers de base de données en fonction du serveur SQL sur lequel vous positionnez les bases de données.
ms.openlocfilehash: 72eebc4523eb538762adcfd3c2ee7138853a80ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819826"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="cc242-104">Installer et créer des bases de données</span><span class="sxs-lookup"><span data-stu-id="cc242-104">Install and Create Databases</span></span>

<span data-ttu-id="cc242-105">Vous sélectionnez les bases de données que vous voulez créer pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="cc242-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="cc242-106">Par défaut, la base de données est créée sur le serveur SQL Server défini dans le site défini et déploie et configure automatiquement les fichiers de base de données en fonction du serveur SQL sur lequel vous positionnez les bases de données.</span><span class="sxs-lookup"><span data-stu-id="cc242-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="cc242-107">**Sélectionnez les bases de données que vous voulez créer**: activez la case à cocher des bases de données que vous souhaitez déployer et configurer.</span><span class="sxs-lookup"><span data-stu-id="cc242-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="cc242-108">Activez les cases à cocher de toutes les bases de données que vous voulez déployer.</span><span class="sxs-lookup"><span data-stu-id="cc242-108">Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="cc242-109">Le serveur SQL doit déjà avoir été configuré pour l’instance (le cas échéant) et les ports de pare-feu doivent être ouverts pour accepter l’instance vers laquelle vous déployez les bases de données.</span><span class="sxs-lookup"><span data-stu-id="cc242-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="cc242-110">Pour plus d’informations, reportez-vous à [configurer SQL Server pour Lync server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="cc242-110">For details, see [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="cc242-111">**Avancé**: cliquez sur le serveur SQL et cliquez sur le bouton **avancé** pour sélectionner les options correspondant aux emplacements des fichiers de base de données sur votre serveur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cc242-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="cc242-112">Pour plus d’informations sur l’emplacement du fichier de base de données avancé, voir [installation de la base de données avec Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="cc242-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="cc242-113">**Retour**: Si vous cliquez sur ce bouton, vous revenez à l’écran précédent (il est possible que vous ne soyez pas toujours disponible en fonction de la manière dont vous êtes parvenu à cette boîte de dialogue).</span><span class="sxs-lookup"><span data-stu-id="cc242-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="cc242-114">**Suivant**: lorsque vous cliquez sur ce bouton, la sélection est validée dans la boîte de dialogue active et vous pouvez accéder à la boîte de dialogue suivante de configuration des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="cc242-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="cc242-115">**Annuler**: lorsque vous cliquez sur ce bouton, les modifications sont ignorées.</span><span class="sxs-lookup"><span data-stu-id="cc242-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="cc242-116">Certains écrans de configuration ne vous invitent pas à vous demander si vous souhaitez quitter et annuler vos modifications.</span><span class="sxs-lookup"><span data-stu-id="cc242-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="cc242-117">Lorsque vous sélectionnez **Oui** , vous fermez la configuration actuelle et vous revenez au générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="cc242-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="cc242-118">Si vous sélectionnez **non** , la boîte de dialogue Configuration actuelle s’affiche pour vous permettre de poursuivre la configuration.</span><span class="sxs-lookup"><span data-stu-id="cc242-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="cc242-119">**Aide**: cliquez sur le bouton **aide** pour afficher les informations d’aide associées à la boîte de dialogue Configuration actuelle.</span><span class="sxs-lookup"><span data-stu-id="cc242-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


