---
title: Ajouter Office Web Apps Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'L’Assistant Définir un nouveau serveur Office Web Apps Server définit un nouveau serveur Office Web Apps Server dans votre déploiement. Vous devez fournir les informations suivantes :'
ms.openlocfilehash: 002566fb77539745d1d0023159e9af7852b1ecdc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119703"
---
# <a name="add-office-web-apps-server"></a>Ajouter Office Web Apps Server

L’Assistant Définir **un nouveau serveur Office Web Apps Server** définit un nouveau serveur Office Web Apps Server dans votre déploiement. Vous devez fournir les informations suivantes :

 Nom de domaine complet **d’Office Web Apps Server**: tapez le nom de domaine complet du serveur qui hébergera le serveur Office Web Apps Server

 URL de découverte **d’Office Web Apps Server**: tapez l’URL (uniform resource locator) complète du serveur Office Web Apps Server

> [!TIP]
> Le comportement par défaut de l’URL de découverte **d’Office Web Apps Server** consiste à créer l’URL en fonction du nom de domaine général (FQDN) du serveur Office Web Apps server au format : `https://<FQDN of the Office Web Apps Server/hosting/discovery` . Dans la plupart des cas, vous ne devrez pas modifier le format par défaut. Vous devrez peut-être modifier le format par défaut si le serveur Office Web Apps Server et l’URL de découverte Office Web Apps Server doivent être différents. Par exemple, votre serveur Office Web Apps Server est placé dans le réseau de périmètre et aura une URL différente en fonction de l’emplacement.

 Office Web Apps Server est déployé dans un réseau externe **(périmètre/Internet)**: cochez la case si votre serveur Office Web Apps Server est placé en dehors de votre pare-feu interne, tel que le réseau de périmètre, le réseau externe ou toute autre zone réseau qui n’est pas la même que votre réseau interne.

## <a name="see-also"></a>Voir aussi

[Composants et topologies pour les conférences](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)