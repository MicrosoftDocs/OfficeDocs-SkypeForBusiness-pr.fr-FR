---
title: Installer et créer des bases de données
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: Vous sélectionnez les bases de données que vous voulez créer pour votre déploiement. Par défaut, la base de données est créée sur le serveur SQL Server défini dans le site défini et déploie et configure automatiquement les fichiers de base de données en fonction du serveur SQL sur lequel vous positionnez les bases de données.
ms.openlocfilehash: f4ee4bb5c5b6dcfe66680fdc163930470f1b50a5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291678"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="935f0-104">Installer et créer des bases de données</span><span class="sxs-lookup"><span data-stu-id="935f0-104">Install and Create Databases</span></span>

<span data-ttu-id="935f0-105">Vous sélectionnez les bases de données que vous voulez créer pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="935f0-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="935f0-106">Par défaut, la base de données est créée sur le serveur SQL Server défini dans le site défini et déploie et configure automatiquement les fichiers de base de données en fonction du serveur SQL sur lequel vous positionnez les bases de données.</span><span class="sxs-lookup"><span data-stu-id="935f0-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="935f0-107">**Sélectionnez les bases de données que vous voulez créer**: activez la case à cocher des bases de données que vous souhaitez déployer et configurer.</span><span class="sxs-lookup"><span data-stu-id="935f0-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="935f0-108">Activez les cases à cocher de toutes les bases de données que vous voulez déployer.</span><span class="sxs-lookup"><span data-stu-id="935f0-108">Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="935f0-109">Le serveur SQL doit déjà avoir été configuré pour l’instance (le cas échéant) et les ports de pare-feu doivent être ouverts pour accepter l’instance vers laquelle vous déployez les bases de données.</span><span class="sxs-lookup"><span data-stu-id="935f0-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="935f0-110">Pour plus d’informations, reportez-vous à [configurer SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="935f0-110">For details, see [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="935f0-111">**Avancé**: cliquez sur le serveur SQL et cliquez sur le bouton **avancé** pour sélectionner les options correspondant aux emplacements des fichiers de base de données sur votre serveur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="935f0-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="935f0-112">Pour plus d’informations sur l’emplacement du fichier de base de données avancé, voir [installation de la base de données avec Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="935f0-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="935f0-113">**Retour**: Si vous cliquez sur ce bouton, vous revenez à l’écran précédent (il est possible que vous ne soyez pas toujours disponible en fonction de la manière dont vous êtes parvenu à cette boîte de dialogue).</span><span class="sxs-lookup"><span data-stu-id="935f0-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="935f0-114">**Suivant**: lorsque vous cliquez sur ce bouton, la sélection est validée dans la boîte de dialogue active et vous pouvez accéder à la boîte de dialogue suivante de configuration des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="935f0-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="935f0-115">**Annuler**: lorsque vous cliquez sur ce bouton, les modifications sont ignorées.</span><span class="sxs-lookup"><span data-stu-id="935f0-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="935f0-116">Certains écrans de configuration ne vous invitent pas à vous demander si vous souhaitez quitter et annuler vos modifications.</span><span class="sxs-lookup"><span data-stu-id="935f0-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="935f0-117">Lorsque vous sélectionnez **Oui** , vous fermez la configuration actuelle et vous revenez au générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="935f0-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="935f0-118">Si vous sélectionnez **non** , la boîte de dialogue Configuration actuelle s’affiche pour vous permettre de poursuivre la configuration.</span><span class="sxs-lookup"><span data-stu-id="935f0-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="935f0-119">**Aide**: cliquez sur le bouton **aide** pour afficher les informations d’aide associées à la boîte de dialogue Configuration actuelle.</span><span class="sxs-lookup"><span data-stu-id="935f0-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


