---
title: Installer le magasin de configurations local
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Pour commencer l’installation d’un nouveau Skype pour le serveur de rôle de serveur d’entreprise, vous devez d’abord installer le serveur SQL local qui va héberger le magasin de configurations local. Le magasin de configurations local agira comme un réplica en lecture seule de la Skype pour le magasin Central de gestion de Business Server (CMS).
ms.openlocfilehash: 5fddc31ac297a6938d242936afcd00ddb3d9fbf9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893671"
---
# <a name="install-local-configuration-store"></a>Installer le magasin de configurations local

Pour commencer l’installation d’un nouveau Skype pour le serveur de rôle de serveur d’entreprise, vous devez d’abord installer le serveur SQL local qui va héberger le magasin de configurations local. Le magasin de configurations local agira comme un réplica en lecture seule de la Skype pour le magasin Central de gestion de Business Server (CMS). Vous devez être connecté au serveur décrit à l’étape **Installer le magasin de configurations local** en tant qu’administrateur local de l’ordinateur ; en outre, vous devez être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Si vous effectuez l’installation sur un serveur Edge, vous n’avez pas besoin d’être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Le document de définition du Générateur de topologie est lu à partir du document exporté définition plutôt qu’à partir du magasin Central de gestion. Pour exporter le document de définition du Générateur de topologie et la rendre disponible pour les serveurs de périphérie, consultez la rubrique[exporter votre topologie et copie sur un support externe de l’Installation Edge](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).

Pour commencer l’installation :

1. Sur la Skype métier de la page, à côté **étape 1 : installer le magasin de Configuration Local**, cliquez sur **exécuter**.

2. Dans la page **Configuration du serveur local** assurez-vous que l’option **Récupérer automatiquement la configuration à partir du magasin central de gestion** est sélectionnée, puis cliquez sur **Suivant**.

3. Une fois l’installation terminée, cliquez sur **Terminer**.

> [!NOTE]
> L’installation de SQL Server local peut prendre un certain temps. Vous ne verrez pas les mises à jour sur progression dans l’écran Résumé pendant l’installation de SQL Server. Si vous souhaitez surveiller la progression de l’installation, utilisez le Gestionnaire des tâches pour surveiller l’installation de SQL Server.


