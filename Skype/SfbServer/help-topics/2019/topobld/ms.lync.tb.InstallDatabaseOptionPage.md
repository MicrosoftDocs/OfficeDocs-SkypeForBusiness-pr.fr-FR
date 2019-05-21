---
title: Page des options Installer une base de données
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Vous pouvez configurer des options avancées pour l’emplacement de la base de données et des fichiers journaux sur votre serveur SQL Server. Les options disponibles sont les suivantes:'
ms.openlocfilehash: 1ac9b4dd2b68c9160eec34459a26f109ba666393
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291657"
---
# <a name="install-database-options-page"></a>Page des options Installer une base de données

Vous pouvez configurer des options avancées pour l’emplacement de la base de données et des fichiers journaux sur votre serveur SQL Server. Les options disponibles sont les suivantes:

> [!IMPORTANT]
> Sélectionnez l’option qui correspond le mieux à vos exigences et aux stratégies relatives au placement des données et du fichier journal sur vos ordinateurs SQL Server.

 **Déterminez automatiquement l’emplacement du fichier de base de données**: l’option par défaut utilise un algorithme qui détermine l’espace disponible sur le serveur SQL et distribue les fichiers de base de données et les fichiers journaux pour des performances optimales.

 **Utiliser les valeurs par défaut des instances SQL Server**: sélectionnez cette option pour placer le fichier de base de données et les fichiers journaux en fonction des paramètres d’instance sur SQL Server. Les options sont généralement gérées et configurées par l’administrateur de votre base de données.

 **Nous devons**suivre le chemin d’accès de la base de données SQL Server cible: sélectionnez cette option pour définir vos propres chemins d’accès pour les fichiers journaux et de base de données SQL Server en entrant le chemin d’accès complet au lecteur et au dossier où les fichiers de base de données et les fichiers journaux seront placés.

> [!IMPORTANT]
> Les chemins d’accès que vous entrez pourront être modifiés en fonction des algorithmes d’optimisation des performances de l’installation. Pour plus d’informations, consultez l' [installation de la base de données à l’aide de Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).

 **OK**: cliquez sur le bouton OK pour valider les modifications.

 **Annuler**: cliquez sur Annuler pour annuler les modifications et revenir à l’écran d’installation de la base de données.

 **Aide**: cliquez sur le bouton aide pour accéder à cette page d’aide.

## <a name="see-also"></a>Voir aussi

[Emplacement des données et du fichier journal SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
