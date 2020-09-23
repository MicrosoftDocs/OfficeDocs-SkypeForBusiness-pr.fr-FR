---
title: Page des options Installer une base de données
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
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: 'Vous configurez les options avancées pour le placement des fichiers de base de données et des fichiers journaux sur votre serveur SQL Server. Les options disponibles sont les suivantes :'
ms.openlocfilehash: 4c8c456aa1fd0e9eee150e184b4d1f7934c26b65
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215305"
---
# <a name="install-database-options-page"></a>Page des options Installer une base de données

Vous configurez les options avancées pour le placement des fichiers de base de données et des fichiers journaux sur votre serveur SQL Server. Les options disponibles sont les suivantes :

> [!IMPORTANT]
> Sélectionnez l’option qui correspond le mieux à vos exigences et stratégies concernant l’emplacement des données et des fichiers journaux sur vos ordinateurs SQL Server.

 **Déterminer automatiquement l’emplacement du fichier de base de données**: l’option par défaut utilise un algorithme qui détermine l’espace disponible sur le serveur SQL et distribue la base de données et les fichiers journaux pour des performances optimales.

 **Utiliser les valeurs par défaut de l’instance SQL Server**: sélectionnez cette option pour placer le fichier de base de données et les fichiers journaux en fonction des paramètres d’instance sur SQL Server. Généralement, les options sont gérées et configurées par votre administrateur de base de données.

 **Nous chemin d’accès sur le serveur SQL Server cible**: sélectionnez cette option pour définir vos propres chemins d’accès pour les fichiers journaux et de base de données SQL Server en tapant le chemin d’accès complet du lecteur et du dossier où seront placés les fichiers de base de données et les fichiers journaux.

> [!IMPORTANT]
> Les chemins d’accès que vous entrez peuvent être modifiés selon les algorithmes d’optimisation de performance dans l’installation. Pour plus d’informations, voir la documentation [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).

 **OK** : Cliquez sur OK pour valider vos modifications.

 **Annuler** : cliquez sur Annuler pour supprimer les modifications et revenir à l’écran Installer une base de données.

 **Aide** : cliquez sur le bouton Aide pour accéder à cette page d’aide.

## <a name="see-also"></a>Voir aussi

[Emplacement des fichiers journaux et des données SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
