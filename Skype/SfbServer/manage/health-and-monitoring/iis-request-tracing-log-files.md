---
title: Surveillance des fichiers journaux de suivi des demandes IIS dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Résumé : Découvrez la prise en charge du service de mobilité (Mcx) dans Skype Entreprise Server 2015 pour les clients hérités.'
ms.openlocfilehash: 5fb9e66efa468e8755fe369c3ce4f2a4b8979e57
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823504"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Surveillance des fichiers journaux de suivi des demandes IIS dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez la prise en charge de Mobility Service (Mcx) dans Skype Entreprise Server 2015 pour les clients hérités.
  
Cette rubrique s’applique uniquement aux déploiements qui ne sont pas destinés aux clients Lync Mobile Lync 2010 et est destinée au service de mobilité (Mcx).

> [!NOTE]
> La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible dans Skype Entreprise Server 2019. Tous les clients mobiles Skype Entreprise actuels utilisent déjà l’API web de communications unifiées (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.
  
Lorsque vous activez le suivi des demandes IIS (Internet Information Services) pour le service de mobilité De Skype Entreprise Server (Mcx), les fichiers journaux générés peuvent consommer jusqu’à trois gigaoctets d’espace disque par jour. La journalisation du suivi IIS est activée par défaut. Vous devez surveiller les serveurs frontux pour vous assurer qu’ils ne manquent pas d’espace disque. 
  
Par défaut, les services Internet (IIS) stockent les fichiers journaux dans %SystemDrive%\inetpub\logs\LogFiles.
  
Pour désactiver le suivi des demandes IIS pour un serveur entier, tapez ce qui suit sur la ligne de commande :
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Pour plus d’informations sur la **commande httpLogging,** voir [la référence de commande.](https://go.microsoft.com/fwlink/p/?linkId=234927)
  

