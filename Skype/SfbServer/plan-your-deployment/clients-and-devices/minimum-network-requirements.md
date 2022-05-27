---
title: Configuration réseau minimale requise pour l’application Réunions Skype
ms.author: serdars
author: SerdarSoysal
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
description: 'Résumé : Informations pour les organisations qui n’utilisent pas Microsoft 365 ou Office 365 et qui doivent accéder aux réunions hébergées par les organisations qui le font.'
ms.openlocfilehash: bdc3c6a3fba4968dd679a2039064c19786bd4661
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674526"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Configuration réseau minimale requise pour l’application Réunions Skype

**Résumé:** Informations pour les organisations qui n’utilisent pas Microsoft 365 ou Office 365 et qui ont besoin d’accéder aux réunions hébergées par les organisations qui le font. Cet article n’est pas destiné aux utilisateurs finaux Office 365 ou Microsoft 365.

Les utilisateurs de l’application réunions Skype dans les organisations qui n’utilisent pas Microsoft 365 ou Office 365 peuvent avoir besoin d’assister à des réunions hébergées dans Skype Entreprise Online. Pour participer à ces réunions, leurs administrateurs réseau doivent autoriser les noms de domaine complets, les adresses IP et les ports suivants via leur pare-feu.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Configuration requise pour la connectivité de l’application Skype Meetings

Les informations répertoriées ici sont un sous-ensemble des informations [contenues dans Office 365 URL et plages d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Cette rubrique est beaucoup plus approfondie et sera toujours à jour.

|Application|Noms de domaine complets de destination|Adresses IP|Ports|
|---|---------|---------|---------|
|**application réunions Skype**|\*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast.officeapps.live.com<span></span> <br/>\*powerpoint.officeapps.live.com<span></span> <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>|Ces adresses IP sont fréquemment mises à jour. Consultez [Skype Entreprise et Microsoft Teams plages d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) ainsi que [Office plages d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges)|TCP : 80 & 443<br/>UDP : 3478-3481|
|**Teams**|\*<span></span>.microsoft.com <br/>\*<span></span>.skype.com|Ces adresses IP sont fréquemment mises à jour. Consultez [Skype Entreprise et Microsoft Teams plages d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) ainsi que [Office plages d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges)|TCP : 443 <br/> UDP : 3478-3481|

## <a name="see-also"></a>Voir aussi
<a name="BKMK_Conferencing"> </a>

[Planifier les clients de réunions (application web et application réunions)](meetings-clients.md)

[Déployer des clients téléchargeables web dans Skype Entreprise Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plateformes prises en charge pour l’application réunions Skype](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
