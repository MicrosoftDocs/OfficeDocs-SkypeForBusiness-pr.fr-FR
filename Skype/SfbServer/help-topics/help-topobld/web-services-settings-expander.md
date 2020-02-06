---
title: Expanseur des paramètres des services web
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
description: Dans le générateur de topologie, vous pouvez modifier les paramètres de port utilisés pour vos services Web internes et externes. De plus, et si vous déployez l’équilibrage de charge DNS (Domain Name System), vous pouvez utiliser le générateur de topologie pour configurer le nom de domaine complet (FQDN) du pool qui se résout aux adresses IP physiques de tous les serveurs du pool.
ms.openlocfilehash: ab2a93bab1717bc34e0df42fb7f4a9ed5298166c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819026"
---
# <a name="web-services-settings-expander"></a>Expanseur des paramètres des services web
 
Dans le générateur de topologie, vous pouvez modifier les paramètres de port utilisés pour vos services Web internes et externes. De plus, et si vous déployez l’équilibrage de charge DNS (Domain Name System), vous pouvez utiliser le générateur de topologie pour configurer le nom de domaine complet (FQDN) du pool qui se résout aux adresses IP physiques de tous les serveurs du pool.
  
### <a name="editing-web-services-settings"></a>Modification des paramètres des services web

1. Sélectionnez le serveur frontal Standard Edition ou le pool frontal Enterprise Edition approprié, puis cliquez sur **Modifier les propriétés**.
    
2. Dans la boîte de dialogue **Modifier les propriétés**, cliquez sur l’onglet **Services web**.
    
    > [!CAUTION]
    > Si vous avez plusieurs pools frontal ou serveur principal, le nom de domaine complet des services Web externes doit être unique. Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que **pool01.contoso.com**, vous ne pouvez pas utiliser **pool01.contoso.com** pour un autre pool frontal ou serveur frontal. Si vous déployez également des directeurs, le nom de domaine complet des services Web externes défini pour n’importe quel directeur ou pool de réalisateur doit être unique à partir d’un autre directeur ou pool de directeurs, ainsi que sur n’importe quel pool frontal ou serveur frontal. Si vous décidez de remplacer les services Web internes par un nom de domaine complet autonome, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool de directeurs.
  
3. Si vous modifiez les propriétés d’un pool Enterprise Edition, vous avez la possibilité de sélectionner **Remplacer le nom de domaine complet**. Ne sélectionnez cette option que si vous utilisez l’équilibrage de la charge DNS. Si vous utilisez l’équilibrage de la charge DNS, sélectionnez **Remplacer le nom de domaine complet**, puis, dans la zone de texte, tapez le nom de domaine complet du pool résolu en adresses IP physiques de tous les serveurs de ce pool. Si vous n’utilisez pas l’équilibrage de la charge DNS et si vous n’avez pas sélectionné **Remplacer le nom de domaine complet**, vous ne pouvez pas modifier le nom de domaine complet des services web internes. Le FQDN des services Web internes est l’URL utilisée par les utilisateurs internes pour se connecter à Skype entreprise Server.
    
4. Vous pouvez aussi entrer de nouvelles valeurs HTTP, HTTPS ou HTTP et HTTPS pour les **ports d’écoute** et les **ports publiés**. Les ports d’écoute sont les ports utilisés par les services Internet (IIS) pour écouter le trafic SIP (Session Initiation Protocol) entrant. Les ports publiés sont des ports configurés sur un programme d’équilibrage de la charge ou un serveur proxy inverse. Ils sont également utilisés pour écouter le trafic SIP entrant. Par défaut, les ports d’écoute et publiés HTTP sont définis sur le port 80. Les ports HTTPS correspondants sont tous deux définis sur le port 443. La valeur par défaut pour les deux ports publiés HTTP est le port 8080 et les ports HTTPS correspondants sont définis sur le port 4443.
    
5. Cliquez sur **OK**.
    
Si vous modifiez le nom de domaine complet interne ou l’un des ports d’écoute affectés, vous devez réexécuter l’installation locale sur tous les serveurs du pool pour que ces modifications prennent effet.
  

