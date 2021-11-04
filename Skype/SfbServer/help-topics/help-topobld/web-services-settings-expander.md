---
title: Expanseur des paramètres des services web
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
description: À partir du Générateur de topologie, vous pouvez modifier les paramètres de port utilisés pour vos services web internes et externes. En outre, si vous déployez l’équilibrage de charge DNS (Domain Name System), vous pouvez utiliser le Générateur de topologie pour configurer le nom de domaine complet (FQDN) du pool qui se résout en adresses IP physiques de tous les serveurs de ce pool.
ms.openlocfilehash: 0d1f97f7ff44e78c5a117ddd65664a479d63a20f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765592"
---
# <a name="web-services-settings-expander"></a>Expandeur des paramètres des services web
 
À partir du Générateur de topologie, vous pouvez modifier les paramètres de port utilisés pour vos services web internes et externes. En outre, si vous déployez l’équilibrage de charge DNS (Domain Name System), vous pouvez utiliser le Générateur de topologie pour configurer le nom de domaine complet (FQDN) du pool qui se résout en adresses IP physiques de tous les serveurs de ce pool.
  
### <a name="editing-web-services-settings"></a>Modification des paramètres des services web

1. Sélectionnez le serveur frontal Standard Edition ou le pool frontal Enterprise Edition approprié, puis cliquez sur **Modifier les propriétés**.
    
2. Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur l’onglet **Services web**.
    
    > [!CAUTION]
    > Si vous avez plusieurs serveurs frontaux ou serveurs frontaux, le nom de groupe des services Web externes doit être unique. Par exemple, si vous définissez le nom de groupe des services Web externes d’un serveur frontal en tant que **pool01.contoso.com,** vous ne pouvez pas utiliser **pool01.contoso.com** pour un autre pool frontal ou serveur frontal. Si vous déployez également des directeurs, le FQDN des services Web externes défini pour n’importe quel directeur ou pool directeur doit être unique à partir de tout autre directeur ou pool directeur, ainsi que de tout pool frontal ou serveur frontal. Si vous décidez de remplacer les services web internes par un FQDN auto-défini, chaque FQDN doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool directeur.
  
3. Si vous modifiez les propriétés d’un pool Enterprise Edition, vous avez la possibilité de choisir **Remplacer le nom de domaine complet**. Ne sélectionnez cette option que si vous utilisez l’équilibrage de la charge DNS. Si vous utilisez l’équilibrage de la charge DNS, sélectionnez **Remplacer le nom de domaine complet**, puis dans la zone de texte, tapez le nom de domaine complet du pool qui est résolu en adresses IP physiques de tous les serveurs de ce pool. Si vous n’utilisez pas l’équilibrage de la charge DNS, et si vous n’avez pas sélectionné **Remplacer le nom de domaine complet**, vous ne pouvez pas modifier le nom de domaine complet des services web internes. Le FQDN des services web internes est l’URL utilisée par les utilisateurs internes pour se connecter à Skype Entreprise Server.
    
4. Vous pouvez aussi entrer de nouvelles valeurs HTTP, HTTPS ou HTTP et HTTPS pour les **Ports d’écoute** et les **Ports publiés**. Les ports d’écoute sont les ports utilisés par les services Internet (IIS) pour écouter le trafic SIP (Session Initiation Protocol) entrant ; les ports publiés sont des ports configurés sur un programme d’équilibrage de la charge ou un serveur proxy inverse et sont également utilisés pour écouter le trafic SIP entrant. Par défaut, les ports d’écoute et publiés HTTP sont définis sur le port 80 ; les ports HTTPS correspondants sont tous deux définis sur 443. La valeur par défaut pour les deux ports publiés HTTP est 8080 et les ports HTTPS correspondants sont définis sur 4443.
    
5. Cliquez sur **OK**.
    
Si vous modifiez le nom de domaine complet interne ou l’un des ports d’écoute assignés, vous devez réexécuter l’installation locale sur tous les serveurs du pool pour que ces modifications prennent effet.
  

