---
title: Installer et créer des bases de données
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: Vous sélectionnez les bases de données que vous voulez créer pour votre déploiement. Par défaut, la base de données est créée sur les SQL Server définies dans le site défini, et déploie et configure automatiquement les fichiers de base de données en fonction de la SQL Server sur qui vous placez les bases de données.
ms.openlocfilehash: 446f23508ccc835d873e0ddd8ec183e80e40450d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386042"
---
# <a name="install-and-create-databases"></a>Installer et créer des bases de données

Vous sélectionnez les bases de données que vous voulez créer pour votre déploiement. Par défaut, la base de données est créée sur les SQL Server définies dans le site défini, et déploie et configure automatiquement les fichiers de base de données en fonction de la SQL Server sur qui vous placez les bases de données.

 **Sélectionnez les bases de données que vous souhaitez créer** : activez la case à cocher de toutes les bases de données que vous envisagez de déployer et de configurer. Activez la case à cocher de certaines ou de toutes les bases de données que vous déploierez.

> [!CAUTION]
> Le SQL Server doit déjà avoir été configuré pour l’instance (le cas besoin) et les ports de pare-feu doivent être ouverts pour prendre en charge l’instance vers qui vous déployez les bases de données. Pour plus d’informations, voir [Configure SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)

 **Avancé** : cliquez sur le SQL Server cliquez sur le bouton Avancé pour  choisir les options des emplacements des fichiers de base de données sur votre SQL Server. Pour plus d’informations sur l’emplacement du fichier de base de données avancé, voir [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)

 **Précédent** : le fait de cliquer sur ce bouton vous permet de revenir à l’écran précédent (il n’est peut-être pas toujours disponible, selon la façon dont vous avez atteint cette boîte de dialogue).

 **Suivant** : le fait de cliquer sur ce bouton valide votre sélection sur la boîte de dialogue active et vous permet d’accéder à la boîte de dialogue suivante pour configurer des informations supplémentaires

 **Annuler** : le fait de cliquer sur ce bouton vous fera quitter cette étape de configuration et annulera vos modifications. Certains écrans, mais pas tous, vous inviteront à quitter et à annuler vos modifications. La sélection **de Oui** ferme la configuration actuelle, ferme la configuration actuelle et vous retourne au Générateur de topologies. En sélectionnant **Non**, vous reviendrez dans la boîte de dialogue active où vous pourrez poursuivre la configuration.

 **Aide** : en cliquant sur le bouton **Aide**, vous affichez les informations d’aide associées à la boîte de dialogue de configuration active.