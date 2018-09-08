---
title: Configuration réseau minimale requise pour l'application Réunions Skype
ms.author: jambirk
author: PhillipGarding
manager: serdars
ms.date: 6/4/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Résumé : Informations pour les organisations qui n’utilisent Office 365 et accéder aux réunions hébergées par les organisations qui effectuent.'
ms.openlocfilehash: 53e4bd52242faa62a14b39474f1859064afcdb43
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882655"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Configuration réseau minimale requise pour l'application Réunions Skype
 
**Résumé :**  Informations pour les organisations qui n’utilisent Office 365 et accéder aux réunions hébergées par les organisations qui effectuent. Cet article n’est pas destiné aux utilisateurs de ces applications.
  
Pour permettre aux utilisateurs d’utiliser Skype réunions App à participer aux réunions hébergées dans Skype pour Business Online, les administrateurs réseau d’organisations qui n’utilisent pas Office 365 doivent liste d’autorisation ou de rendre disponibles les noms de domaine complets, les adresses IP et les ports mentionnées ci-dessous.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Configuration requise pour la connectivité de l'application Réunions Skype

Les informations répertoriées ici sont un sous-ensemble des [plages d’adresses IP et Office 365 URL](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)qui fournit plus de détails et qui sera toujours le plus à jour.
                    
 
|Application |Noms de domaine complets de destination  |Adresses IP  |Ports  |
|---|---------|---------|---------|
|**Application Réunions Skype** | \*. lync.com <br/>\*. infra.lync.com<br/>\*. pipe.aria.microsoft.com<br/>\*. sfbassets.com<br/>\*. msecnd.net<br/>\*diffusion<span></span>. officeapps.live.com <br/>\*PowerPoint<span></span>. officeapps.live.com <br/>\*. office.live.com<br/>\*. cdn.office.net<br/>*.s-microsoft.com<br/>        |   Ces adresses IP sont régulièrement mises à jour.  Voir [Skype pour les plages d’adresses IP Business](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) ainsi que les [Plages d’adresses IP Office Online](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |Port TCP : 80 &amp; 443<br/>UDP : 3478 à 3481<br/>
|**Teams**    | \*<span></span>. microsoft.com <br/>\*<span></span>. skype.com | Ces adresses IP sont régulièrement mises à jour.  Voir [Skype pour les plages d’adresses IP Business](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) ainsi que les [Plages d’adresses IP Office Online](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP : 443 <br/> UDP : 3478 à 3481

## <a name="see-also"></a>Voir aussi
<a name="BKMK_Conferencing"> </a>

[Planifier pour les clients de réunions (application Web et application de réunions)](meetings-clients.md)

[Déployer des clients Web téléchargeables Skype pour Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plateformes prises en charge pour l’application de réunions Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)