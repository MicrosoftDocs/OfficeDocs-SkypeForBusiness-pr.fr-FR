---
title: Page des options Installer une base de données
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Vous configurez des options avancées pour l’emplacement des fichiers de base de données et des fichiers journaux sur SQL Server. Les options disponibles sont les suivantes :'
ms.openlocfilehash: 5da2d50bf6571408f63403998443155307d86e2b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805734"
---
# <a name="install-database-options-page"></a>Page des options Installer une base de données

Vous configurez des options avancées pour l’emplacement des fichiers de base de données et des fichiers journaux sur SQL Server. Les options disponibles sont les suivantes :

> [!IMPORTANT]
> Sélectionnez l’option qui correspond le mieux à vos exigences et stratégies relatives à l’emplacement des données et des fichiers journaux sur SQL Server ordinateurs.

 **Déterminer** automatiquement l’emplacement du fichier de base de données : l’option par défaut utilise un algorithme qui détermine l’espace disponible sur le SQL Server et distribue la base de données et les fichiers journaux pour des performances optimales.

 **Utilisez SQL Server défaut de l’instance**: sélectionnez cette option pour placer les fichiers de base de données et les fichiers journaux en fonction des paramètres de l’instance SQL Server. Généralement, les options sont gérées et configurées par votre administrateur de base de données.

 Us **these path on target SQL Server :** Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.

> [!IMPORTANT]
> Les chemins d’accès que vous entrez peuvent être modifiés selon les algorithmes d’optimisation de performance dans l’installation. Pour plus d’informations, voir la documentation [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).

 **OK** : Cliquez sur OK pour valider vos modifications.

 **Annuler** : cliquez sur Annuler pour supprimer les modifications et revenir à l’écran Installer une base de données.

 **Aide** : cliquez sur le bouton Aide pour accéder à cette page d’aide.

## <a name="see-also"></a>Voir aussi

[Emplacement des fichiers journaux et des données SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
