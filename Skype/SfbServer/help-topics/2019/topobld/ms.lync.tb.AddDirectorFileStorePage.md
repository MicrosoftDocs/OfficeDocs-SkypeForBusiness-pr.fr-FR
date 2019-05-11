---
title: Ajouter un magasin de fichiers pour les directeurs
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
ROBOTS: NOINDEX, NOFOLLOW
description: Vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour les directeurs. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou indiquer un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel le partage de fichiers doit se trouver et un nom de dossier pour le nouveau partage de fichiers.
ms.openlocfilehash: f55feb2c05b16c8a6ee98261f5054c1eeeab5178
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33889128"
---
# <a name="add-director-file-store"></a>Ajouter un magasin de fichiers pour les directeurs

Vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour les directeurs. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou indiquer un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel le partage de fichiers doit se trouver et un nom de dossier pour le nouveau partage de fichiers.

> [!IMPORTANT]
> Lorsque vous ajoutez des directeurs à une topologie, la publication de la topologie a besoin d’un accès approprié pour installer le magasin de fichiers et configurer des listes de contrôle d’accès discrétionnaire (DACL) sur le partage de fichiers à utiliser pour le magasin de fichiers. À cet effet, lorsque vous exécutez le générateur de topologie et que vous publiez la nouvelle topologie, vous devez être connecté avec un compte disposant d’autorisations de contrôle intégrales (lecture/écriture/modification) pour le partage de fichiers.

Pour plus d’informations sur la prise en charge du stockage pour les partages de fichiers, reportez-vous à la rubrique [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) de la documentation de prise en charge et à la rubrique [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) de la documentation du déploiement. Pour plus d’informations sur la colocalisation du partage de fichiers, reportez-vous à la rubrique [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) de la documentation de prise en charge. Pour plus d’informations sur la conception de la topologie pour les directeurs, reportez-vous à la rubrique [Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) de la documentation de déploiement.


