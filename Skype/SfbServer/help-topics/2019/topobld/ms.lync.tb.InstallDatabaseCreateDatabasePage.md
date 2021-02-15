---
title: Installer et créer des bases de données
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: Vous sélectionnez les bases de données que vous voulez créer pour votre déploiement. Par défaut, la base de données est créée sur le SQL Server défini dans le site défini, et déploie et configure automatiquement les fichiers de base de données en fonction de la SQL Server sur qui vous placez les bases de données.
ms.openlocfilehash: 4d7a6e4f67dd6b97c8f5f837589af7b096da50b5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835714"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="3aeb7-104">Installer et créer des bases de données</span><span class="sxs-lookup"><span data-stu-id="3aeb7-104">Install and Create Databases</span></span>

<span data-ttu-id="3aeb7-105">Vous sélectionnez les bases de données que vous voulez créer pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="3aeb7-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="3aeb7-106">Par défaut, la base de données est créée sur le SQL Server défini dans le site défini, et déploie et configure automatiquement les fichiers de base de données en fonction de la SQL Server sur qui vous placez les bases de données.</span><span class="sxs-lookup"><span data-stu-id="3aeb7-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="3aeb7-p103">**Sélectionnez les bases de données que vous souhaitez créer** : activez la case à cocher de toutes les bases de données que vous envisagez de déployer et de configurer. Activez la case à cocher de certaines ou de toutes les bases de données que vous déploierez.</span><span class="sxs-lookup"><span data-stu-id="3aeb7-p103">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure. Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="3aeb7-109">Le SQL Server doit déjà avoir été configuré pour l’instance (le cas besoin) et les ports de pare-feu doivent être ouverts pour prendre en charge l’instance vers qui vous déployez les bases de données.</span><span class="sxs-lookup"><span data-stu-id="3aeb7-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="3aeb7-110">Pour plus d’informations, [voir Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="3aeb7-110">For details, see [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="3aeb7-111">**Avancé**: cliquez sur le SQL Server  cliquez sur le bouton Avancé pour choisir les options des emplacements des fichiers de base de données sur votre SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3aeb7-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="3aeb7-112">Pour plus d’informations sur l’emplacement du fichier de base de données avancé, voir [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="3aeb7-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="3aeb7-113">**Précédent** : le fait de cliquer sur ce bouton vous permet de revenir à l’écran précédent (il n’est peut-être pas toujours disponible, selon la façon dont vous avez atteint cette boîte de dialogue).</span><span class="sxs-lookup"><span data-stu-id="3aeb7-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="3aeb7-114">**Suivant** : le fait de cliquer sur ce bouton valide votre sélection sur la boîte de dialogue active et vous permet d’accéder à la boîte de dialogue suivante pour configurer des informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="3aeb7-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="3aeb7-115">**Annuler** : le fait de cliquer sur ce bouton vous fera quitter cette étape de configuration et annulera vos modifications.</span><span class="sxs-lookup"><span data-stu-id="3aeb7-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="3aeb7-116">Certains écrans, mais pas tous, vous inviteront à quitter et à annuler vos modifications.</span><span class="sxs-lookup"><span data-stu-id="3aeb7-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="3aeb7-117">La sélection **de Oui** ferme la configuration actuelle, ferme la configuration actuelle et vous retourne au Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="3aeb7-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="3aeb7-118">En sélectionnant **Non**, vous reviendrez dans la boîte de dialogue active où vous pourrez poursuivre la configuration.</span><span class="sxs-lookup"><span data-stu-id="3aeb7-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="3aeb7-119">**Aide** : en cliquant sur le bouton **Aide**, vous affichez les informations d’aide associées à la boîte de dialogue de configuration active.</span><span class="sxs-lookup"><span data-stu-id="3aeb7-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


