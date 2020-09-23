---
title: Ajouter un magasin de fichiers frontal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
description: Vous devez indiquer un partage de fichiers à utiliser comme magasin de fichiers pour le serveur Standard Edition ou le pool frontal Enterprise Edition. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou indiquer un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers.
ms.openlocfilehash: 4e2c732e0003f23cf183374880592ccd24fbe9bb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218345"
---
# <a name="add-front-end-file-store"></a>Ajouter un magasin de fichiers frontal

Vous devez indiquer un partage de fichiers à utiliser comme magasin de fichiers pour le serveur Standard Edition ou le pool frontal Enterprise Edition. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou indiquer un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers.

> [!IMPORTANT]
> Le partage de fichiers ne peut pas se trouver sur le serveur frontal Enterprise Edition, mais il peut se trouver sur un serveur Standard Edition Server.

> [!IMPORTANT]
> Avant de créer le partage de fichiers, vous pouvez le définir dans le Générateur de topologie, mais vous devez créer le partage de fichiers à l’emplacement que vous définissez avant de publier la topologie.

> [!IMPORTANT]
> Lorsque vous ajoutez un pool frontal Enterprise Edition ou un serveur Standard Edition à votre topologie, le Générateur de topologie doit être en mesure de configurer le magasin de fichiers et de configurer des listes de contrôle d’accès discrétionnaire (DACL) sur le partage de fichiers à utiliser pour le magasin de fichiers. Pour cela, lorsque vous exécutez le Générateur de topologie pour publier la nouvelle topologie, vous devez être connecté avec un compte qui dispose des autorisations de contrôle complètes (lecture/écriture/modification) pour le partage de fichiers.

Pour plus d’informations sur la prise en charge du stockage pour les partages de fichiers, voir [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) dans la documentation de prise en charge et l' [emplacement des fichiers journaux et des données SQL Server](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) dans la documentation de déploiement. Pour plus d’informations sur la colocalisation du partage de fichiers, voir [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) dans la documentation de prise en charge. Pour plus d’informations sur la conception de la topologie pour un pool frontal Enterprise Edition, voir [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) dans la documentation de déploiement.


