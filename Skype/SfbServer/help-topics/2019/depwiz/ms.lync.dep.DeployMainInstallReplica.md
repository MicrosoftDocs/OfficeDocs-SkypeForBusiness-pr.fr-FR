---
title: Installer le magasin de configurations local
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Pour commencer l’installation d’un nouveau serveur de rôles Skype entreprise Server, vous devez d’abord installer le serveur SQL Server local qui hébergera le magasin de configuration local. Le magasin de configuration local fera office de réplica en lecture seule du magasin de gestion centralisé de Skype entreprise Server (CMS).
ms.openlocfilehash: 699294889008f0d353e1ba727cbc078f9616f4ec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303403"
---
# <a name="install-local-configuration-store"></a>Installer le magasin de configurations local

Pour commencer l’installation d’un nouveau serveur de rôles Skype entreprise Server, vous devez d’abord installer le serveur SQL Server local qui hébergera le magasin de configuration local. Le magasin de configuration local fera office de réplica en lecture seule du magasin de gestion centralisé de Skype entreprise Server (CMS). Vous devez être connecté au serveur décrit à l’étape **Installer le magasin de configurations local** en tant qu’administrateur local de l’ordinateur ; en outre, vous devez être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Si vous effectuez l’installation sur un serveur Edge, vous n’avez pas besoin d’être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Le document de définition du générateur de topologie sera lu à partir du document de définition exporté plutôt que du magasin central de gestion. Pour exporter le document de définition du générateur de topologie et le mettre à la disposition des serveurs de périphérie, voir la rubrique[exporter votre topologie et copier celle-ci sur des éléments multimédias externes pour l’installation Edge](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).

Pour commencer l’installation :

1. Dans la page Skype entreprise Server, en regard de la page **étape suivante: installer le magasin de configuration local**, cliquez sur **exécuter**.

2. Dans la page **Configuration du serveur local** assurez-vous que l’option **Récupérer automatiquement la configuration à partir du magasin central de gestion** est sélectionnée, puis cliquez sur **Suivant**.

3. Une fois l’installation terminée, cliquez sur **Terminer**.

> [!NOTE]
> L’installation du serveur local SQL Server peut prendre un certain temps. Vous ne verrez pas les mises à jour en cours dans l’écran Résumé de l’installation lors de l’installation de SQL Server. Si vous souhaitez surveiller la progression de l’installation, utilisez le gestionnaire des tâches pour consulter la configuration de SQL Server.


