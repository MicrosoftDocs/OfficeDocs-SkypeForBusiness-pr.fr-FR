---
title: Skype Entreprise client sur Mac
ms.author: v-mahoffman
author: HowlinWolf-92
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Lisez cette rubrique pour en savoir plus sur la configuration matérielle, logicielle et d’infrastructure requise pour l’Skype Entreprise sur un Mac.
ms.openlocfilehash: b7d3ce484ea3e333e85c2f8473cdcdaaebe44057
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847217"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype Entreprise client sur Mac
 
Lisez cette rubrique pour en savoir plus sur la configuration matérielle, logicielle et d’infrastructure requise pour l’Skype Entreprise sur un Mac.
  
Le [Skype Entreprise client Mac est](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) disponible en téléchargement.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Configuration matérielle et logicielle requise pour Skype Entreprise sur Mac

Le Skype Entreprise client Mac nécessite Mac OS X El Capitan et des niveaux supérieurs, et utilise au moins 100 Mo d’espace disque. Nous supportons l’utilisation de tous les périphériques audio et vidéo intégrés. Les appareils externes doivent être répertoriés à [l Microsoft Teams périphériques.](https://www.microsoft.com/microsoft-teams/across-devices/devices) 
  
> [!NOTE]
> Cette liste est préliminaire et certains appareils peuvent être qualifiés pour Lync, mais ne sont pas pris en charge Skype Entreprise sur Mac. Reportez-vous [à la configuration système](https://products.office.com/office-system-requirements) requise pour le matériel minimal requis.
  
### <a name="legacy-mac-clients"></a>Clients Mac hérités

Skype Entreprise Server 2015 prend également en charge les clients hérités suivants sur les ordinateurs exécutant Mac OS 10.5.8 ou les systèmes d’exploitation ou version la plus récente (le système d’exploitation Mac OS 10.9 n’est actuellement pas pris en charge). Pour plus d’informations sur les fonctionnalités pris en charge, voir comparaison des fonctionnalités client de bureau [pour Skype Entreprise](desktop-feature-comparison.md).
  
- Microsoft Lync pour Mac 2011 (voir le Guide de déploiement [de Lync pour Mac 2011)](/previous-versions/office/office-for-mac-2011/jj984275(v=office.14))
    
- Microsoft Communicator pour Mac 2011 (voir Communicator [pour Mac 2011 Deployment Guide)](/previous-versions/office/office-for-mac-2011/jj984270(v=office.14))
 
Ces clients ne sont pas pris en charge Skype Entreprise Server 2019.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Conditions requises pour l’infrastructure Skype Entreprise sur Mac
<a name="Infrastructure"> </a>

Le client Skype Entreprise Mac tire parti de la plateforme de gestion des communications unifiées (UCMP) et de l’API web de communications unifiées (UCWA) que nos clients de mobilité utilisent.
  
Le client a les mêmes exigences que nos clients de mobilité dans la mesure où vous devez avoir un serveur Edge d’accès et un proxy inverse déployés dans une configuration prise en charge. 
  
### <a name="authentication"></a>Authentification

Le client Skype Entreprise Mac prend en charge l’authentification basée sur les certificats, l’authentification moderne Microsoft et l’authentification multifacteur lorsqu’elles sont déployées et activées.
  
> [!NOTE]
> En raison d’une limitation actuelle, les informations d’identification Exchange utilisateur doivent être identiques à leurs informations d’identification Skype Entreprise données. 
  
### <a name="certificates"></a>Certificats

Les certificats utilisés sur le serveur Edge d’accès, le proxy inverse et le serveur frontal ne doivent pas utiliser l’algorithme de hachage SHA-512.
  
La liste de révocation de certificats HTTP doit être définie et accessible par le client. Par exemple, nous ne prenons pas en charge une entrée LDAP dans le certificat en tant que liste de révocation de certificats.
  
### <a name="dns"></a>DNS

La mobilité doit être correctement déployée pour que le Skype Entreprise sur le client Mac fonctionne correctement. Un scénario d’échec courant consiste à résoudre les deux entrées DNS suivantes sur le réseau interne :
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
Pour plus d’informations, voir : [Deploying Mobility in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility), and the [Microsoft Lync Server 2010 Mobility Guide](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Voir aussi
<a name="Infrastructure"> </a>

[DNS requirements for Skype Entreprise Server](../../plan-your-deployment/network-requirements/dns.md)

[Forum Aux Questions](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problèmes connus](https://go.microsoft.com/fwlink/p/?LinkId=798228)