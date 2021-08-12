---
title: Installer le magasin de configurations local
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Pour commencer l’installation d’un nouveau serveur de rôles Skype Entreprise Server 2015, vous devez d’abord installer le SQL Server local qui hébergera le magasin de configurations local. Le magasin de configurations local agit comme un réplica en lecture seule du magasin central de gestion Skype Entreprise Server (CMS). Vous devez être connecté en tant qu’administrateur local sur le serveur sur lequel vous exécutez l’étape Installer le magasin de configurations local, et être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Si vous effectuez l’installation sur un serveur de périphérie, il n’est pas nécessaire que vous soyez membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Le document de définition du Générateur de topologie sera lu à partir du document de définition exporté et non du magasin central de gestion. Pour exporter le document de définition du Générateur de topologie et le rendre disponible pour les serveurs Edge, consultez la rubrique Exporter votre topologie et la copier sur un support externe pour l’installation Edge.
ms.openlocfilehash: 62318febe6f6c9028e55b19da0c1be6ca6316d2bf372f78bb95931693028a096
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54311662"
---
# <a name="install-local-configuration-store"></a>Installer le magasin de configurations local

Pour commencer l’installation d’un nouveau serveur de rôles Skype Entreprise Server 2015, vous devez d’abord installer le SQL Server local qui hébergera le magasin de configurations local. Le magasin de configurations local agit comme un réplica en lecture seule du magasin central de gestion Skype Entreprise Server (CMS). Vous devez être connecté en tant qu’administrateur local sur le serveur sur lequel vous exécutez l’étape **Installer le magasin de configurations local**, et être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Si vous effectuez l’installation sur un serveur de périphérie, il n’est pas nécessaire que vous soyez membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Le document de définition du Générateur de topologie sera lu à partir du document de définition exporté et non du magasin central de gestion. Pour exporter le document de définition du Générateur de topologie et le rendre disponible pour les serveurs Edge, consultez la rubrique Exporter votre topologie et la copier sur un support externe pour [l’installation Edge.](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation)

Pour commencer l’installation :

1. Dans la page Skype Entreprise Server 2015, à côté de l’étape 1 : Installer le magasin **de configurations local,** cliquez sur **Exécuter**.

2. Dans la page **Configuration du serveur local**, assurez-vous que l’option **Récupérer automatiquement la configuration à partir du magasin central de gestion** est sélectionnée, puis cliquez sur **Suivant**.

3. Une fois l’installation terminée, cliquez sur **Terminer**.

> [!NOTE]
> L’installation du SQL Server local peut prendre un certain temps. Vous ne verrez pas les mises à jour sur la progression dans l’écran récapitulatif de l’installation pendant SQL Server est en cours d’installation. Si vous souhaitez surveiller la progression de l’installation, utilisez le Gestionnaire des tâches pour surveiller SQL Server configuration.