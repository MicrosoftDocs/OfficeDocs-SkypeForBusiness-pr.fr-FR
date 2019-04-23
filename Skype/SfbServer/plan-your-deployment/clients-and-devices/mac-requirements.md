---
title: Skype pour les entreprises sur la configuration requise des clients Mac
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Lisez cette rubrique pour en savoir plus sur la configuration matérielle, logicielle et l’infrastructure pour Skype pour les entreprises en cours d’exécution sur un Mac.
ms.openlocfilehash: bd8522684131d1119ce91c100a2aeeeec4797a70
ms.sourcegitcommit: 920a7dbdc2a0ede94d0a4bd573c01a1ccd838b7e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "31993556"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype pour les entreprises sur la configuration requise des clients Mac
 
Lisez cette rubrique pour en savoir plus sur la configuration matérielle, logicielle et l’infrastructure pour Skype pour les entreprises en cours d’exécution sur un Mac.
  
Le [Skype pour les entreprises sur Mac Client](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3#Mac) est disponible en téléchargement.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Configuration matérielle et logicielle requise pour Skype pour les entreprises sur Mac

Le Skype pour les entreprises sur client Mac requiert Mac OS X El Capitan et versions ultérieures et utilise au moins 100 Mo d’espace disque. Nous prenons en charge l’utilisation de tous les périphériques audio et vidéo intégrés. Périphériques externes doivent être le [Skype pour le catalogue de Solutions métiers](https://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
> [!NOTE]
> Cette liste est préliminaire et certains périphériques peuvent être qualifiés pour Lync, mais pas pris en charge sur Skype pour les entreprises sur le Mac. Reportez-vous à la [configuration système requise](https://products.office.com/en-us/office-system-requirements) pour la configuration matérielle minimale requise.
  
### <a name="legacy-mac-clients"></a>Clients Mac hérités

Skype pour Business Server 2015 prend également en charge les clients hérités suivants sur les ordinateurs qui exécutent Mac OS 10.5.8 ou le dernier service pack ou la dernière version (basé sur Intel) de systèmes d’exploitation (système d’exploitation de Mac OS 10.9 n'est pas actuellement pris en charge). Pour plus d’informations sur les fonctionnalités prises en charge, voir [comparaison des fonctionnalités client de bureau pour Skype pour les entreprises](desktop-feature-comparison.md).
  
- Microsoft Lync pour Mac 2011 (voir [Lync pour Mac 2011 déploiement Guide](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Microsoft Communicator pour Mac 2011 (voir [Communicator pour Mac 2011 déploiement Guide](https://go.microsoft.com/fwlink/p/?LinkId=268787))
 
Ces clients ne sont pas pris en charge par Skype pour Business Server 2019.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Conditions d’infrastructure requises pour Skype pour les entreprises sur Mac
<a name="Infrastructure"> </a>

Le Skype pour les entreprises sur client Mac s’appuie sur la plate-forme de gestion des Communications (UCMP) unifiée ainsi que l’Unified Communications Web API (UCWA) qui utilisent nos clients de mobilité.
  
Ce client requiert la même configuration que nos clients de mobilité, à savoir un serveur Edge d’accès et un proxy inverse déployés dans une configuration prise en charge. 
  
### <a name="authentication"></a>Authentification

Le Skype pour les entreprises sur client Mac prend en charge l’authentification basée sur les certificats, authentification moderne de Microsoft et l’authentification multifacteur lorsque déployé et activé.
  
> [!NOTE]
> En raison d’une limitation actuelle, les informations d’identification de l’utilisateur Exchange doivent être identique à leur Skype pour les informations d’identification de l’entreprise. 
  
### <a name="certificates"></a>Certificats

Les certificats utilisés sur les serveurs Edge d’accès, proxy inverse et frontaux ne doivent pas utiliser l’algorithme de hachage SHA-512.
  
La liste de révocation de certificats HTTP doit être définie et le client doit pouvoir y accéder. Par exemple, nous ne prend en charge une entrée LDAP dans le certificat en tant que votre liste de révocation de certificats.
  
### <a name="dns"></a>DNS

Mobilité doit être correctement déployée pour la Skype pour les entreprises sur le client Mac fonctionne correctement. Il arrive fréquemment qu’une panne survienne car les deux entrées DNS suivantes sont résolvables sur le réseau interne :
  
- lyncdiscoverinternal. \<sipdomain\>
    
- lyncdiscover. \<sipdomain\>
    
Pour plus d’informations, reportez-vous à : [Déploiement de mobilité dans Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)et le [Guide de mobilité de Microsoft Lync Server 2010](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Voir aussi
<a name="Infrastructure"> </a>

[Enregistrements DNS requis pour Skype pour Business Server](../../plan-your-deployment/network-requirements/dns.md)

[Forum aux Questions](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problèmes connus](https://go.microsoft.com/fwlink/p/?LinkId=798228)
