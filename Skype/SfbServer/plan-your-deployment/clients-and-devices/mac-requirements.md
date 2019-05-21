---
title: Configuration requise pour le client Skype entreprise pour Mac
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Consultez cette rubrique pour en savoir plus sur les configurations matérielles, logicielles et d’infrastructure requises pour l’utilisation de Skype entreprise sur Mac.
ms.openlocfilehash: 690e2a568c71d4af98b7d2bf9b9cc2e9919d99e9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277334"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Configuration requise pour le client Skype entreprise pour Mac
 
Consultez cette rubrique pour en savoir plus sur les configurations matérielles, logicielles et d’infrastructure requises pour l’utilisation de Skype entreprise sur Mac.
  
Le [client Skype entreprise pour Mac](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3#Mac) est disponible en téléchargement.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Configuration matérielle et logicielle requise pour Skype entreprise sur Mac

Le client Skype entreprise pour Mac nécessite Mac OS X El Capitan et version ultérieure et utilise au moins 100 Mo d’espace disque. Nous prenons en charge l’utilisation de tous les périphériques audio et vidéo intégrés. Les périphériques externes doivent figurer dans le [catalogue de solutions Skype entreprise](https://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
> [!NOTE]
> Cette liste est une version préliminaire qui peut être homologuée pour Lync et ne peut pas être prise en charge par Skype entreprise sur Mac. Reportez-vous à la [Configuration système requise](https://products.office.com/en-us/office-system-requirements) pour le matériel minimum requis.
  
### <a name="legacy-mac-clients"></a>Clients hérités de Mac

Skype entreprise Server 2015 prend également en charge les clients hérités suivants sur les ordinateurs qui exécutent Mac OS 10.5.8 ou le Service Pack ou la version antérieure (le système d’exploitation Intel) (système d’exploitation Mac OS 10,9 n’est pas pris en charge pour le moment). Pour plus d’informations sur les fonctionnalités prises en charge, voir [comparaison des fonctionnalités de client de bureau pour Skype entreprise](desktop-feature-comparison.md).
  
- Microsoft Lync pour Mac 2011 (voir le [Guide de déploiement de Lync pour mac 2011](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Microsoft Communicator pour Mac 2011 (voir le [Guide de déploiement de Communicator pour mac 2011](https://go.microsoft.com/fwlink/p/?LinkId=268787))
 
Ces clients ne sont pas pris en charge par Skype entreprise Server 2019.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Exigences d’infrastructure pour Skype entreprise sur Mac
<a name="Infrastructure"> </a>

Le client Skype entreprise pour Mac tire parti de la plateforme de gestion des communications unifiées (UCMP), ainsi que de l’API UCWA (Unified Communications Web API) utilisée par nos clients mobiles.
  
Ce client requiert la même configuration que nos clients de mobilité, à savoir un serveur Edge d’accès et un proxy inverse déployés dans une configuration prise en charge. 
  
### <a name="authentication"></a>Authentification

Le client Skype entreprise pour Mac prend en charge l’authentification par certificat, l’authentification moderne Microsoft et l’authentification multifacteur lors du déploiement et de l’activation.
  
> [!NOTE]
> En raison d’une limitation actuelle, les informations d’identification d’Exchange de l’utilisateur doivent être identiques à celles de Skype entreprise. 
  
### <a name="certificates"></a>Certificats

Les certificats utilisés sur les serveurs Edge d’accès, proxy inverse et frontaux ne doivent pas utiliser l’algorithme de hachage SHA-512.
  
La liste de révocation de certificats HTTP doit être définie et le client doit pouvoir y accéder. Par exemple, nous ne prenons pas en charge une entrée LDAP dans le certificat en tant que liste de révocation de certificats.
  
### <a name="dns"></a>DNS

Pour fonctionner correctement, la mobilité doit être déployée correctement pour le client Skype entreprise sur Mac. Il arrive fréquemment qu’une panne survienne car les deux entrées DNS suivantes sont résolvables sur le réseau interne :
  
- lyncdiscoverinternal. \<sipdomain\>
    
- lyncdiscover. \<sipdomain\>
    
Pour plus d’informations, reportez-vous à la rubrique [déploiement de mobilité dans Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)et [Guide de mobilité Microsoft Lync Server 2010](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Voir aussi
<a name="Infrastructure"> </a>

[Configuration requise pour le service DNS pour Skype entreprise Server](../../plan-your-deployment/network-requirements/dns.md)

[Forum aux questions](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problèmes connus](https://go.microsoft.com/fwlink/p/?LinkId=798228)
