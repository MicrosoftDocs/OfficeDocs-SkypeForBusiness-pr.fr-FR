---
title: Ajouter un magasin de fichiers pour les directeurs
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
ROBOTS: NOINDEX, NOFOLLOW
description: Vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour les directeurs. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou indiquer un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers.
ms.openlocfilehash: f134d561a948dbdb89ce655d59e5d5fc205bcbf4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811884"
---
# <a name="add-director-file-store"></a>Ajouter un magasin de fichiers pour les directeurs

Vous devez spécifier un partage de fichiers à utiliser comme magasin de fichiers pour les directeurs. Vous pouvez utiliser un partage de fichiers existant pour le magasin de fichiers ou indiquer un nouveau partage de fichiers en spécifiant le nom de domaine complet (FQDN) du serveur de fichiers sur lequel situer le partage de fichiers et un nom de dossier pour le nouveau partage de fichiers.

> [!IMPORTANT]
> Lorsque vous ajoutez des directeurs à une topologie, la publication de la topologie a besoin d’un accès approprié pour installer le magasin de fichiers et configurer des listes de contrôle d’accès discrétionnaire (DACL) sur le partage de fichiers à utiliser pour le magasin de fichiers. Pour cela, lorsque vous exécutez le Générateur de topologies et publiez la nouvelle topologie, vous devez être connecté avec un compte qui dispose des autorisations de contrôle complètes (lecture/écriture/modification) pour le partage de fichiers.

Pour plus d’informations sur la [](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) prise en charge du stockage pour les partages de fichiers, voir La prise en charge du stockage de fichiers dans la documentation de prise en charge et SQL Server Données et [emplacement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) des fichiers journaux dans la documentation de déploiement. Pour plus d’informations sur la colocalisation du partage de fichiers, voir [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) dans la documentation de prise en charge. Pour plus d’informations sur la conception de la topologie pour les directeurs, voir [Définir](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) un directeur unique dans le Générateur de topologies dans la documentation de déploiement.


