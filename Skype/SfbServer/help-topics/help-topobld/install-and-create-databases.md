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
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: Vous sélectionnez les bases de données que vous voulez créer pour votre déploiement. Par défaut, la base de données est créée sur le serveur SQL Server défini dans le site défini et déploiera et configurera automatiquement les fichiers de base de données en fonction du serveur SQL Server sur lequel vous placez les bases de données.
ms.openlocfilehash: ade264fcda73df408f6bb323dd1e3733ccdd45f1
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215385"
---
# <a name="install-and-create-databases"></a>Installer et créer des bases de données

Vous sélectionnez les bases de données que vous voulez créer pour votre déploiement. Par défaut, la base de données est créée sur le serveur SQL Server défini dans le site défini et déploiera et configurera automatiquement les fichiers de base de données en fonction du serveur SQL Server sur lequel vous placez les bases de données.

 **Sélectionnez les bases de données que vous souhaitez créer** : activez la case à cocher de toutes les bases de données que vous envisagez de déployer et de configurer. Activez la case à cocher de certaines ou de toutes les bases de données que vous déploierez.

> [!CAUTION]
> Le serveur SQL Server doit déjà avoir été configuré pour l’instance (le cas échéant) et des ports de pare-feu doivent être ouverts pour accueillir l’instance sur laquelle vous déployez les bases de données. Pour plus d’informations, voir [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)

 **Avancé**: cliquez sur le serveur SQL, puis cliquez sur le bouton **avancé** pour choisir les options des emplacements des fichiers de base de données sur votre serveur SQL Server. Pour plus d’informations sur l’emplacement du fichier de base de données avancé, voir [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)

 **Précédent** : le fait de cliquer sur ce bouton vous permet de revenir à l’écran précédent (il n’est peut-être pas toujours disponible, selon la façon dont vous avez atteint cette boîte de dialogue).

 **Suivant** : le fait de cliquer sur ce bouton valide votre sélection sur la boîte de dialogue active et vous permet d’accéder à la boîte de dialogue suivante pour configurer des informations supplémentaires

 **Annuler** : le fait de cliquer sur ce bouton vous fera quitter cette étape de configuration et annulera vos modifications. Certains écrans, mais pas tous, vous inviteront à quitter et à annuler vos modifications. Si vous sélectionnez **Oui** , la configuration actuelle est fermée et la configuration actuelle est fermée et vous revenez au générateur de topologie. En sélectionnant **Non**, vous reviendrez dans la boîte de dialogue active où vous pourrez poursuivre la configuration.

 **Aide** : en cliquant sur le bouton **Aide**, vous affichez les informations d’aide associées à la boîte de dialogue de configuration active.


