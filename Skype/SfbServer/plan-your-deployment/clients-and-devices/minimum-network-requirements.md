---
title: Configuration réseau minimale requise pour l'application Réunions Skype
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Résumé: informations pour les organisations qui n’utilisent pas Office 365 et qui ont besoin d’accéder à des réunions hébergées par d’autres organisations.'
ms.openlocfilehash: 1017c81fc3432fbd409077b89809d725b2b0e2cc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277481"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Configuration réseau minimale requise pour l'application Réunions Skype
 
**Résumé:**  Informations pour les organisations qui n’utilisent pas Office 365 et qui ont besoin d’accéder à des réunions hébergées par d’autres organisations. Cet article n’est pas destiné aux utilisateurs de ces applications.
  
Pour permettre aux utilisateurs d’utiliser l’application réunions Skype pour participer aux réunions hébergées dans Skype entreprise Online, les administrateurs réseau d’organisations qui n’utilisent pas Office 365 doivent procéder à la liste blanche ou rendre disponibles les noms de domaine complets (FQDN), IPs et ports indiqués ci-dessous.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Configuration requise pour la connectivité de l'application Réunions Skype

Les informations ci-dessous sont un sous-ensemble d' [URL et de plages d’adresses IP Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), qui offre une plus grande profondeur et sont toujours les plus à jour.
                    
 
|Appli |Noms de domaine complets de destination  |Adresses IP  |Ports  |
|---|---------|---------|---------|
|**Application Réunions Skype** | \*. lync.com <br/>\*. infra.lync.com<br/>\*. pipe.aria.microsoft.com<br/>\*. sfbassets.com<br/>\*. msecnd.net<br/>\*Broadcast<span></span>. officeapps.live.com <br/>\*PowerPoint<span></span>. officeapps.live.com <br/>\*. office.live.com<br/>\*. cdn.office.net<br/>*.s-microsoft.com<br/>        |   Ces adresses IP sont régulièrement mises à jour.  Afficher les [plages d’adresses IP de Skype entreprise](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) et les [plages d’adresses IP d’Office Online](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP : 3478 à 3481<br/>
|**Teams**    | \*<span></span>. microsoft.com <br/>\*<span></span>. skype.com | Ces adresses IP sont régulièrement mises à jour.  Afficher les [plages d’adresses IP de Skype entreprise](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) et les [plages d’adresses IP d’Office Online](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP : 443 <br/> UDP : 3478 à 3481

## <a name="see-also"></a>Voir aussi
<a name="BKMK_Conferencing"> </a>

[Planifier pour les clients de conférences (application Web et application réunions)](meetings-clients.md)

[Déploiement de clients Web à télécharger dans Skype entreprise Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plates-formes prises en charge pour l’application réunions Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
