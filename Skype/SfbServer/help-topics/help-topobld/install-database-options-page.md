---
title: Page des options Installer une base de données
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: 'Vous configurez les options avancées pour l’emplacement des fichiers journaux et de base de données sur votre serveur SQL Server. Les options disponibles sont les suivants :'
ms.openlocfilehash: 17453e97bf527390ed2dab561c3995711d7b1d07
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888610"
---
# <a name="install-database-options-page"></a>Page des options Installer une base de données

Vous configurez les options avancées pour l’emplacement des fichiers journaux et de base de données sur votre serveur SQL Server. Les options disponibles sont les suivants :

> [!IMPORTANT]
> Sélectionnez l’option qui convient le mieux à vos exigences et les stratégies relatives à l’emplacement des fichiers journaux et de données sur les ordinateurs SQL Server.

 **Déterminer automatiquement le dossier de base de données**: l’option par défaut utilise un algorithme qui détermine l’espace disponible sur le serveur SQL Server et les distribue les fichiers journaux et de base de données pour des performances optimales.

 **Utiliser SQL Server instance par défaut**: sélectionnez cette option pour placer le fichier de base de données et les journaux basés sur les paramètres de l’instance à SQL Server. Les options sont généralement gérées et configurées par votre administrateur de base de données.

 **Nous ces chemin d’accès sur le serveur SQL Server cible**: sélectionnez cette option pour définir vos propres chemins d’accès pour les fichiers journaux et de base de données SQL Server en tapant le chemin d’accès complet au lecteur et au dossier où les fichiers journaux et de base de données seront passés.

> [!IMPORTANT]
> Les chemins d’accès que vous entrez peuvent être modifiés en fonction des algorithmes d’optimisation de performances de l’installation. Pour plus d’informations, voir la [Base de données Installation à l’aide de Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).

 **OK**: cliquez sur le bouton OK pour valider vos modifications.

 **Annuler**: cliquez sur Annuler pour annuler toutes les modifications et revenir à l’écran installer une base de données.

 **Aide**: cliquez sur le bouton aide pour accéder à cette page d’aide.

## <a name="see-also"></a>Voir aussi

[Emplacement des fichiers journaux et données SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
