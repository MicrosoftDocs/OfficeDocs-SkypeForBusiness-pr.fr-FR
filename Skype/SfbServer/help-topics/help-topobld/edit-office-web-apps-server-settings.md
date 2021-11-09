---
title: Modifier les paramètres Office Web Apps Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 8/19/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.OfficeWebAppsServerSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 7a4b91ff-ca11-4dde-852d-ec51d143968a
description: 'Vous modifiez les propriétés du serveur Office Web Apps Server. Les propriétés suivantes peuvent être modifiées :'
ms.openlocfilehash: 7174dbb5949bd8e8033193adf21267fa0735f99b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860341"
---
# <a name="edit-office-web-apps-server-settings"></a>Modifier les paramètres Office Web Apps Server

Vous modifiez les propriétés du serveur Office Web Apps Server. Les propriétés suivantes peuvent être modifiées :

 **Office Nom** de domaine complet du serveur Web Apps Server : cette propriété définit le nom de domaine complet du serveur Office Web Apps Server et doit correspondre à un enregistrement A ou AAAA d’hôte DNS (si IPv6 est utilisé).

 **Office WEB Apps Server discovery URL**: URL (Uniform Resource Locator) pour l’accès client au serveur Office Web Apps Server, vous devrez peut-être modifier cette adresse par défaut si le serveur est placé dans une autre zone réseau que le réseau interne pour votre déploiement.

Activez la case à cocher **Le serveur Office Web Apps Server est déployé sur un réseau externe (périmètre/Internet)** si le serveur est déployé dans le réseau de votre périmètre ou dans une autre zone réseau qui se situe à l’extérieur de votre pare-feu interne séparant le réseau de périmètre, les réseaux moyennement fiables et Internet de votre déploiement interne.

![Office Expandeur de Paramètres Web Apps.](../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a>Voir aussi

[Composants et topologies pour les conférences](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)