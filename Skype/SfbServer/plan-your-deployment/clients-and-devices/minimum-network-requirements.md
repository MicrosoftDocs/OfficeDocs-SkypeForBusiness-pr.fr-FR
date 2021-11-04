---
title: Configuration réseau minimale requise pour l’application Réunions Skype
ms.author: v-mahoffman
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Résumé : Informations pour les organisations qui n’utilisent pas Microsoft 365 ou Office 365 et qui ont besoin d’accéder aux réunions hébergées par des organisations qui le font.'
ms.openlocfilehash: 2d27e578e448c44cd13190d4aedf1e15f611d997
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751573"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Configuration réseau minimale requise pour l’application Réunions Skype
 
**Résumé :**  Informations pour les organisations qui n’utilisent pas Microsoft 365 ou Office 365 et qui ont besoin d’accéder aux réunions hébergées par des organisations qui le font. Cet article n’est pas destiné aux utilisateurs de ces applications.
  
Pour permettre aux utilisateurs d’utiliser l’application Skype Meetings pour participer à des réunions hébergées dans Skype Entreprise Online, les administrateurs réseau des organisations qui n’utilisent pas Microsoft 365 ou Office 365 doivent autoriser ou mettre à disposition les FQDN, les fai et les ports mentionnés ci-dessous.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Conditions requises Skype de l’application Réunions

Les informations répertoriées ici sont un sous-ensemble d’URL Office 365 et de [plages d’adresses IP,](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)qui fournit plus de profondeur et sera toujours la plus à jour.
                    
 
|Application |FQDN de destination  |Adresses IP  |Ports  |
|---|---------|---------|---------|
|**Application Réunions Skype** | \*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast <span></span> .officeapps.live.com <br/>\*powerpoint <span></span> .officeapps.live.com <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>        |   Ces adresses IP sont fréquemment mises à jour.  Voir [Skype Entreprise plages d’adresses IP,](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) ainsi que [Office plages d’adresses IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP : 80 &amp; 443<br/>UDP : 3478-3481<br/>
|**Teams**    | \*<span></span>.microsoft.com <br/>\*<span></span>.skype.com | Ces adresses IP sont fréquemment mises à jour.  Voir [Skype Entreprise plages d’adresses IP,](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) ainsi que [Office plages d’adresses IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP : 443 <br/> UDP : 3478-3481

## <a name="see-also"></a>Voir aussi
<a name="BKMK_Conferencing"> </a>

[Planifier les clients Meetings (application Web et application réunions)](meetings-clients.md)

[Déployer des clients web téléchargeables dans Skype Entreprise Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plateformes prise en charge pour Skype Application Réunions](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
