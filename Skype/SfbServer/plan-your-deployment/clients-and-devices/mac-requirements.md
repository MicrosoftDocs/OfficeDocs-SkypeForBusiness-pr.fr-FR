---
title: Skype pour le commerce sur la configuration du client Mac
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Lisez cette rubrique pour en savoir plus sur le matériel, les logiciels et les exigences de l’infrastructure pour l’exécution de Skype pour entreprise sur un Mac.
ms.openlocfilehash: 1b5fa68a9618126ab69f4ca78f13e65f1ab3ee4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype pour le commerce sur la configuration du client Mac
 
Lisez cette rubrique pour en savoir plus sur le matériel, les logiciels et les exigences de l’infrastructure pour l’exécution de Skype pour entreprise sur un Mac.
  
Le [Skype pour entreprise sur le Client Mac](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3#Mac) est disponible au téléchargement.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-the-mac"></a>Configuration matérielle et logicielle requise pour Skype Entreprise sur Mac

Le Skype pour entreprise sur le client Mac nécessite Mac OS X El Capitan et ultérieure et utilise au moins 100 Mo d’espace disque. Nous prenons en charge l’utilisation de tous les périphériques audio et vidéo intégrés. Périphériques externes doivent figurer sur la [liste des périphériques qualifiés pour une utilisation avec Lync](https://go.microsoft.com/fwlink/p/?LinkId=798223). 
  
> [!NOTE]
> Cette liste est préliminaire et certains périphériques peuvent être qualifiés de Lync, mais non pris en charge par Skype pour entreprises sur le Mac. > Voir la [configuration système requise](https://products.office.com/en-us/office-system-requirements) pour la configuration matérielle minimale requise.
  
### <a name="legacy-mac-clients"></a>Clients Mac hérités

Skype pour Business Server 2015 prend également en charge les clients hérités suivants sur les ordinateurs exécutant Mac OS 10.5.8 ou le dernier service pack ou la mise à jour (Intel) systèmes d’exploitation (système d’exploitation de Mac OS 10.9 n'est pas actuellement pris en charge). Pour plus d’informations sur les fonctionnalités prises en charge, consultez [comparaison des fonctionnalités client de bureau pour Skype pour les entreprises](desktop-feature-comparison.md).
  
- Microsoft Lync pour Mac 2011 (voir [Lync pour Mac 2011 Deployment Guide](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Communicator Microsoft pour Mac 2011 (voir [Communicator pour Mac 2011 Deployment Guide](https://go.microsoft.com/fwlink/p/?LinkId=268787))
    
## <a name="infrastructure-requirements-for-skype-for-business-on-the-mac"></a>Configuration requise pour l’infrastructure pour Skype Entreprise sur Mac
<a name="Infrastructure"> </a>

Le Skype pour entreprise sur le client Mac s’appuie sur la plate-forme de gestion des Communications (UCMP) unifiée ainsi que l’Unified Communications Web API (UCWA) destiné à nos clients de mobilité.
  
Ce client requiert la même configuration que nos clients de mobilité, à savoir un serveur Edge d’accès et un proxy inverse déployés dans une configuration prise en charge. En outre, la mobilité doit être activée pour votre compte.
  
### <a name="authentication"></a>Authentification

Le Skype pour entreprise sur le client Mac prend en charge l’authentification NTLM. De plus, il prend aussi en charge l’authentification moderne de Microsoft et l’authentification à plusieurs facteurs lorsqu’elles sont déployées et activées.
  
> [!NOTE]
> En raison d’une limitation actuelle, informations d’identification de l’utilisateur Exchange doivent être le même que leur Skype pour les informations d’identification de l’entreprise. 
  
### <a name="certificates"></a>Certificats

Les certificats utilisés sur les serveurs Edge d’accès, proxy inverse et frontaux ne doivent pas utiliser l’algorithme de hachage SHA-512.
  
La liste de révocation de certificats HTTP doit être définie et le client doit pouvoir y accéder. Par exemple, nous ne prennent en charge une entrée LDAP dans le certificat de votre liste de révocation de certificats.
  
### <a name="dns"></a>DNS

Mobilité doit être déployée correctement pour le Skype pour entreprise sur le client Mac pour fonctionner correctement. Il arrive fréquemment qu’une panne survienne car les deux entrées DNS suivantes sont résolvables sur le réseau interne :
  
- lyncdiscoverinternal. \<sipdomain\>
    
- lyncdiscover. \<sipdomain\>
    
Pour plus d’informations, reportez-vous à la rubrique : [Mobilité de déploiement de Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)et le [Guide de mobilité de Microsoft Lync Server 2010](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Voir aussi
<a name="Infrastructure"> </a>

#### 

[Configuration requise par DNS Skype pour Business Server 2015](../../plan-your-deployment/network-requirements/dns.md)
#### 

[Forum aux Questions](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problèmes connus](https://go.microsoft.com/fwlink/p/?LinkId=798228)

