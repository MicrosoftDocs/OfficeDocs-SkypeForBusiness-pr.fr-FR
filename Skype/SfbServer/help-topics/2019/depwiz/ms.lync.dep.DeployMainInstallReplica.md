---
title: Installer le magasin de configurations local
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
  - ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
f1.keywords:
  - CSH
ms.localizationpriority: medium
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Pour commencer l’installation d’un nouveau serveur de rôles Skype Entreprise Server, vous devez d’abord installer le SQL Server local qui hébergera le magasin de configurations local. Le magasin de configurations local agit comme un réplica en lecture seule du magasin central de gestion Skype Entreprise Server (CMS).'
---

# <a name="install-local-configuration-store"></a>Installer le magasin de configurations local

Pour commencer l’installation d’un nouveau serveur de rôles Skype Entreprise Server, vous devez d’abord installer le SQL Server local qui hébergera le magasin de configurations local. Le magasin de configurations local agit comme un réplica en lecture seule du magasin central de gestion Skype Entreprise Server (CMS). Vous devez être connecté en tant qu’administrateur local sur le serveur sur lequel vous exécutez l’étape **Installer le magasin de configurations local**, et être membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Si vous effectuez l’installation sur un serveur de périphérie, il n’est pas nécessaire que vous soyez membre du groupe RTCUniversalServerAdmins ou RTCUniversalGlobalReadOnlyGroup. Le document de définition du Générateur de topologie sera lu à partir du document de définition exporté et non du magasin central de gestion. Pour exporter le document de définition du Générateur de topologie et le rendre disponible pour les serveurs Edge, consultez la [rubriqueExporter](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation) votre topologie et la copier sur un support externe pour l’installation Edge.

Pour commencer l’installation :

1. Dans la page Skype Entreprise Server, à côté de **l’étape 1 : Installer le magasin de configurations local**, cliquez sur **Exécuter**.

2. Dans la page **Configuration du serveur local**, assurez-vous que l’option **Récupérer automatiquement la configuration à partir du magasin central de gestion** est sélectionnée, puis cliquez sur **Suivant**.

3. Une fois l’installation terminée, cliquez sur **Terminer**.

> [!NOTE]
> L’installation du SQL Server local peut prendre un certain temps. Les mises à jour de la progression ne s’afficheront pas dans l’écran récapitulatif de l’installation pendant SQL Server’installation. Si vous souhaitez surveiller la progression de l’installation, utilisez le Gestionnaire des tâches pour surveiller SQL Server configuration.