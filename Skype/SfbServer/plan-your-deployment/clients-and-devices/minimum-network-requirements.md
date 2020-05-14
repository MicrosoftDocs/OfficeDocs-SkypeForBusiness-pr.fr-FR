---
title: Configuration réseau minimale requise pour l’application Réunions Skype
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Résumé : informations pour les organisations qui n’utilisent pas Microsoft 365 ou Office 365 et qui ont besoin d’accéder à des réunions hébergées par des organisations qui le font.'
ms.openlocfilehash: 656f8fa52f4a1080cca0b8464becf77c8c2a0ef0
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219724"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Configuration réseau minimale requise pour l’application Réunions Skype
 
**Résumé :**  Informations pour les organisations qui n’utilisent pas Microsoft 365 ou Office 365 et qui ont besoin d’accéder à des réunions hébergées par des organisations qui le font. Cet article n’est pas destiné aux utilisateurs de ces applications.
  
Pour permettre aux utilisateurs d’utiliser l’application réunions Skype pour participer à des réunions hébergées dans Skype entreprise Online, les administrateurs réseau des organisations qui n’utilisent pas Microsoft 365 ou Office 365 doivent être autorisés à accéder à la liste des noms de domaine complets, des adresses IP et des ports mentionnés ci-dessous.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Configuration requise pour la connectivité des applications Skype meetings

Les informations répertoriées ici sont un sous-ensemble des [URL et des plages d’adresses IP Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), ce qui fournit davantage de détails et sera toujours le plus à jour.
                    
 
|Application |Noms de domaine complets de destination  |Adresses IP  |Ports  |
|---|---------|---------|---------|
|**Application Réunions Skype** | \*. lync.com <br/>\*. infra.lync.com<br/>\*. pipe.aria.microsoft.com<br/>\*. sfbassets.com<br/>\*. msecnd.net<br/>\*Broadcast <span></span> . officeapps.live.com <br/>\*PowerPoint <span></span> . officeapps.live.com <br/>\*. office.live.com<br/>\*. cdn.office.net<br/>*. s-microsoft.com<br/>        |   Ces adresses IP sont fréquemment mises à jour.  Voir [plages d’adresses IP Skype entreprise](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) et [plages d’adresses IP Office](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP : 80 &amp; 443<br/>UDP : 3478-3481<br/>
|**Teams**    | \*<span></span>. microsoft.com <br/>\*<span></span>. skype.com | Ces adresses IP sont fréquemment mises à jour.  Voir [plages d’adresses IP Skype entreprise](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) et [plages d’adresses IP Office](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP : 443 <br/> UDP : 3478-3481

## <a name="see-also"></a>Voir aussi
<a name="BKMK_Conferencing"> </a>

[Planifier les clients des réunions (application Web et application de réunion)](meetings-clients.md)

[Déploiement de clients Web téléchargeables dans Skype entreprise Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plateformes prises en charge pour l’application réunions Skype](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
