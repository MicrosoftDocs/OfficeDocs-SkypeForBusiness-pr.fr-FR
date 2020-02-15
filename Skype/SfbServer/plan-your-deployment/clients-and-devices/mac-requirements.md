---
title: Configuration requise pour les clients Skype entreprise sur Mac
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Lisez cette rubrique pour en savoir plus sur les exigences en matière de matériel, de logiciel et d’infrastructure pour l’exécution de Skype entreprise sur Mac.
ms.openlocfilehash: f4f62246a86dabeb628755d3c75a10bc285ede12
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42013457"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Configuration requise pour les clients Skype entreprise sur Mac
 
Lisez cette rubrique pour en savoir plus sur les exigences en matière de matériel, de logiciel et d’infrastructure pour l’exécution de Skype entreprise sur Mac.
  
Le [client Skype entreprise sur Mac](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) est disponible en téléchargement.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Configuration matérielle et logicielle requise pour Skype entreprise sur Mac

Le client Skype entreprise sur Mac requiert Mac OS X El Capitan et les versions ultérieures, et utilise au moins 100 Mo d’espace disque. Nous prenons en charge l’utilisation de tous les périphériques audio et vidéo intégrés. Les périphériques externes doivent se trouver dans le [catalogue de solutions Skype entreprise](https://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
> [!NOTE]
> Cette liste est préliminaire et certains appareils peuvent être qualifiés pour Lync, mais ne sont pas pris en charge par Skype entreprise sur Mac. Reportez-vous à la [Configuration système requise](https://products.office.com/office-system-requirements) pour la configuration matérielle minimale requise.
  
### <a name="legacy-mac-clients"></a>Clients hérités Mac

Skype entreprise Server 2015 prend également en charge les clients hérités suivants sur des ordinateurs exécutant le système d’exploitation Mac OS 10.5.8 ou version plus récente (le système d’exploitation Mac OS 10,9 n’est actuellement pas pris en charge). Pour plus d’informations sur les fonctionnalités prises en charge, consultez la rubrique [Desktop Client Feature Comparison for Skype for Business](desktop-feature-comparison.md).
  
- Microsoft Lync pour Mac 2011 (voir le [Guide de déploiement de Lync pour Mac 2011](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Microsoft Communicator pour Mac 2011 (voir le [Guide de déploiement de Communicator pour mac 2011](https://go.microsoft.com/fwlink/p/?LinkId=268787))
 
Ces clients ne sont pas pris en charge par Skype entreprise Server 2019.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Configuration requise pour l’infrastructure pour Skype entreprise sur Mac
<a name="Infrastructure"> </a>

Le client Skype entreprise sur Mac tire parti de la plateforme de gestion des communications unifiées (UCMP) et de l’API Web Unified Communications (UCWA) que nos clients de mobilité utilisent.
  
Le client a les mêmes exigences que nos clients de mobilité, car vous devez disposer d’un serveur Edge d’accès et d’un proxy inverse déployé dans une configuration prise en charge. 
  
### <a name="authentication"></a>Authentification

Le client Skype entreprise sur Mac prend en charge l’authentification basée sur le certificat, l’authentification moderne Microsoft et l’authentification multifacteur lors du déploiement et de l’activation de l’authentification multifacteur.
  
> [!NOTE]
> En raison d’une limite actuelle, les informations d’identification Exchange de l’utilisateur doivent être identiques à leurs informations d’identification Skype entreprise. 
  
### <a name="certificates"></a>Certificats

Les certificats en cours d’utilisation sur le serveur Edge d’accès, le proxy inverse et les serveurs frontaux ne doivent pas utiliser l’algorithme de hachage SHA-512.
  
La liste de révocation de certificats HTTP doit être définie et accessible par le client. Par exemple, nous ne prenons pas en charge une entrée LDAP dans le certificat en tant que liste de révocation de certificats.
  
### <a name="dns"></a>DNS

La mobilité doit être correctement déployée pour que Skype entreprise sur le client Mac fonctionne correctement. Un scénario d’échec courant consiste à faire en sorte que les deux entrées DNS suivantes soient réactivées sur le réseau interne :
  
- lyncdiscoverinternal. \<sipdomain\>
    
- lyncdiscover. \<sipdomain\>
    
Pour plus d’informations, reportez-vous à la rubrique suivante : [Deploying Mobility in Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)et le [Guide de mobilité de Microsoft Lync Server 2010](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Voir aussi
<a name="Infrastructure"> </a>

[Configuration DNS requise pour Skype entreprise Server](../../plan-your-deployment/network-requirements/dns.md)

[Forum Aux Questions](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problèmes connus](https://go.microsoft.com/fwlink/p/?LinkId=798228)
