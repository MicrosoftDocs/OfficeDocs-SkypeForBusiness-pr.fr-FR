---
title: Surveillance des fichiers journaux de suivi des demandes IIS Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: 'Résumé : Découvrez le service de mobilité (Mcx) dans Skype Entreprise Server 2015 pour les clients hérités.'
ms.openlocfilehash: 2b571ceb583f7a42c6f41fba3c868fbe1628631a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857551"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>Surveillance des fichiers journaux de suivi des demandes IIS Skype Entreprise Server 2015
 
**Résumé :** Découvrez le service de mobilité (Mcx) dans Skype Entreprise Server 2015 pour les clients hérités.
  
Cette rubrique s’applique uniquement aux déploiements qui ne sont pas destinés aux clients Lync Mobile Lync 2010 et est destinée au service de mobilité (Mcx).

> [!NOTE]
> La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible Skype Entreprise Server 2019. Tous les clients mobiles Skype Entreprise actuellement utilisent déjà l’API UCWA (Unified Communications Web API) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.
  
Lorsque vous activez le suivi des demandes Internet Information Services (IIS) pour le service de mobilité Skype Entreprise Server (Mcx), les fichiers journaux générés peuvent consommer jusqu’à trois gigaoctets d’espace disque par jour. La journalisation du suivi IIS est activée par défaut. Vous devez surveiller les serveurs frontux pour vous assurer qu’ils ne manquent pas d’espace disque. 
  
Par défaut, les services Internet (IIS) stockent les fichiers journaux dans %SystemDrive%\inetpub\logs\LogFiles.
  
Pour désactiver le suivi des demandes IIS pour un serveur entier, tapez ce qui suit sur la ligne de commande :
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

Pour plus d’informations sur la **commande httpLogging,** voir [la référence de commande.](/previous-versions/iis/settings-schema/aa347466(v=vs.90))
