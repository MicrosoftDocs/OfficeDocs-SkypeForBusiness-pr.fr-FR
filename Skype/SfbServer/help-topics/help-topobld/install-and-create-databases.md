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
# <a name="install-and-create-databases"></a>Installer et créer des bases de données

Vous sélectionnez les bases de données que vous voulez créer pour votre déploiement. Par défaut, la base de données est créée sur le serveur SQL Server défini dans le site défini et déploie et configure automatiquement les fichiers de base de données en fonction du serveur SQL sur lequel vous positionnez les bases de données.

 **Sélectionnez les bases de données que vous voulez créer**: activez la case à cocher des bases de données que vous souhaitez déployer et configurer. Activez les cases à cocher de toutes les bases de données que vous voulez déployer.

> [!CAUTION]
> Le serveur SQL doit déjà avoir été configuré pour l’instance (le cas échéant) et les ports de pare-feu doivent être ouverts pour accepter l’instance vers laquelle vous déployez les bases de données. Pour plus d’informations, reportez-vous à [configurer SQL Server pour Lync server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)

 **Avancé**: cliquez sur le serveur SQL et cliquez sur le bouton **avancé** pour sélectionner les options correspondant aux emplacements des fichiers de base de données sur votre serveur SQL Server. Pour plus d’informations sur l’emplacement du fichier de base de données avancé, voir [installation de la base de données avec Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)

 **Retour**: Si vous cliquez sur ce bouton, vous revenez à l’écran précédent (il est possible que vous ne soyez pas toujours disponible en fonction de la manière dont vous êtes parvenu à cette boîte de dialogue).

 **Suivant**: lorsque vous cliquez sur ce bouton, la sélection est validée dans la boîte de dialogue active et vous pouvez accéder à la boîte de dialogue suivante de configuration des informations supplémentaires.

 **Annuler**: lorsque vous cliquez sur ce bouton, les modifications sont ignorées. Certains écrans de configuration ne vous invitent pas à vous demander si vous souhaitez quitter et annuler vos modifications. Lorsque vous sélectionnez **Oui** , vous fermez la configuration actuelle et vous revenez au générateur de topologie. Si vous sélectionnez **non** , la boîte de dialogue Configuration actuelle s’affiche pour vous permettre de poursuivre la configuration.

 **Aide**: cliquez sur le bouton **aide** pour afficher les informations d’aide associées à la boîte de dialogue Configuration actuelle.


