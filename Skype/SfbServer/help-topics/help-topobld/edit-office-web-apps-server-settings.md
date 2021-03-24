---
title: Modifier les paramètres Office Web Apps Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/19/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.OfficeWebAppsServerSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7a4b91ff-ca11-4dde-852d-ec51d143968a
description: 'Vous modifiez les propriétés d’Office Web Apps Server configuré. Les propriétés suivantes peuvent être modifiées :'
ms.openlocfilehash: e9f4a188c5cb58be685db4ea44157f2897ebe5ba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095538"
---
# <a name="edit-office-web-apps-server-settings"></a>Modifier les paramètres Office Web Apps Server

Vous modifiez les propriétés d’Office Web Apps Server configuré. Les propriétés suivantes peuvent être modifiées :

 Nom de domaine complet **(FQDN) d’Office Web Apps Server**: cette propriété définit le nom de domaine complet d’Office Web Apps Server et doit correspondre à un enregistrement A ou AAAA (si IPv6 est utilisé) d’hôte DNS (domain name system).

 **URL** de découverte Office Web Apps Server : URL (Uniform Resource Locator) pour l’accès client à Office Web Apps Server, vous devrez peut-être modifier cette adresse par défaut si le serveur est placé dans une autre zone réseau que le réseau interne pour votre déploiement.

Activez la case à cocher **Le serveur Office Web Apps Server est déployé sur un réseau externe (périmètre/Internet)** si le serveur est déployé dans le réseau de votre périmètre ou dans une autre zone réseau qui se situe à l’extérieur de votre pare-feu interne séparant le réseau de périmètre, les réseaux moyennement fiables et Internet de votre déploiement interne.

![Expandeur des paramètres Office Web Apps](../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a>Voir aussi

[Composants et topologies pour les conférences](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)