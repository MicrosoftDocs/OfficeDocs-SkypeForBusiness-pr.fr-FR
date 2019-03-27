---
title: Ajouter un magasin de fichiers du serveur d’archivage
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: Pour activer l’archivage du contenu de messagerie instantanée et de conférence web (réunion), vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour les copies de l’ensemble du contenu de conférence web (réunion). Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers d’archivage ou indiquer un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel le partage de fichiers doit se trouver et un nom de dossier pour le nouveau partage de fichiers.
ms.openlocfilehash: ae120bf9d3b17cd7b7ec06c32d22c4a77076c047
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877901"
---
# <a name="add-archiving-server-file-store"></a>Ajouter un magasin de fichiers du serveur d’archivage

Pour activer l’archivage du contenu de messagerie instantanée et de conférence web (réunion), vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour les copies de l’ensemble du contenu de conférence web (réunion). Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers d’archivage ou indiquer un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel le partage de fichiers doit se trouver et un nom de dossier pour le nouveau partage de fichiers.

> [!IMPORTANT]
> Avant de créer le partage de fichiers, vous pouvez le définir dans le générateur de topologie, mais vous devez créer le partage de fichiers à l’emplacement défini avant la publication de la topologie. > lorsque vous ajoutez un serveur d’archivage à votre topologie, le Générateur de topologie doit être en mesure de définir le magasin de fichiers d’archivage et de configurer des listes de contrôle d’accès discrétionnaire (DACL) sur le partage de fichiers à utiliser pour le magasin de fichiers. À cet effet, lorsque vous exécutez le générateur de topologie pour publier la nouvelle topologie, vous devez être connecté avec un compte disposant d’autorisations de contrôle intégrales (lecture/écriture/modification) pour le partage de fichiers.

Pour plus d’informations sur la prise en charge du stockage pour les partages de fichiers, reportez-vous à la rubrique [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) de la documentation de prise en charge et à la rubrique [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) de la documentation de déploiement. Pour plus d’informations sur la colocalisation du partage de fichiers, reportez-vous à la rubrique [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) de la documentation de prise en charge.


