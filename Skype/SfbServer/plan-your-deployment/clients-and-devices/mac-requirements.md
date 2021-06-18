---
title: 'Skype Entreprise sur Mac : exigences en matière de client'
ms.author: v-cichur
author: cichur
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
description: Lisez cette rubrique pour en savoir plus sur la configuration matérielle, logicielle et d’infrastructure requise pour l’exécution de Skype Entreprise sur un Mac.
ms.openlocfilehash: 866eda0cc5e82db1da1b69bee3eb4bf26df6d7b2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109280"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype Entreprise sur Mac : exigences en matière de client
 
Lisez cette rubrique pour en savoir plus sur la configuration matérielle, logicielle et d’infrastructure requise pour l’exécution de Skype Entreprise sur un Mac.
  
Le [client Skype Entreprise sur Mac](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) est disponible en téléchargement.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Configuration matérielle et logicielle requise pour Skype Entreprise sur Mac

Le client Skype Entreprise sur Mac nécessite Mac OS X El Capitan et une valeur supérieure, et utilise au moins 100 Mo d’espace disque. Nous supportons l’utilisation de tous les périphériques audio et vidéo intégrés. Les appareils externes doivent se trouver dans le [catalogue de solutions Skype Entreprise.](https://partnersolutions.skypeforbusiness.com/solutionscatalog) 
  
> [!NOTE]
> Cette liste est préliminaire et certains appareils peuvent être qualifiés pour Lync, mais ne sont pas pris en charge sur Skype Entreprise sur Mac. Reportez-vous [à la configuration système](https://products.office.com/office-system-requirements) requise pour le matériel minimal requis.
  
### <a name="legacy-mac-clients"></a>Clients Mac hérités

Skype Entreprise Server 2015 prend également en charge les clients hérités suivants sur les ordinateurs qui exécutent Mac OS 10.5.8 ou les systèmes d’exploitation ou version la plus récente (basé sur Intel) (le système d’exploitation Mac OS 10.9 n’est actuellement pas pris en charge). Pour plus d’informations sur les fonctionnalités prise en charge, voir Comparaison des fonctionnalités client de [bureau pour Skype Entreprise.](desktop-feature-comparison.md)
  
- Microsoft Lync pour Mac 2011 (voir le Guide de déploiement [de Lync pour Mac 2011)](/previous-versions/office/office-for-mac-2011/jj984275(v=office.14))
    
- Microsoft Communicator pour Mac 2011 (voir Communicator [pour Mac 2011 Deployment Guide)](/previous-versions/office/office-for-mac-2011/jj984270(v=office.14))
 
Ces clients ne sont pas pris en charge par Skype Entreprise Server 2019.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Conditions d’infrastructure requises pour Skype Entreprise sur Mac
<a name="Infrastructure"> </a>

Le client Skype Entreprise sur Mac tire parti de la plateforme de gestion des communications unifiées (UCMP) et de l’API web de communications unifiées (UCWA) que nos clients de mobilité utilisent.
  
Le client a les mêmes exigences que nos clients de mobilité dans la mesure où vous devez avoir un serveur Edge d’accès et un proxy inverse déployés dans une configuration prise en charge. 
  
### <a name="authentication"></a>Authentification

Le client Skype Entreprise sur Mac prend en charge l’authentification basée sur les certificats, l’authentification moderne Microsoft et l’authentification multifacteur lorsqu’elles sont déployées et activées.
  
> [!NOTE]
> En raison d’une limitation actuelle, les informations d’identification Exchange de l’utilisateur doivent être identiques à leurs informations d’identification Skype Entreprise. 
  
### <a name="certificates"></a>Certificats

Les certificats utilisés sur le serveur Edge d’accès, le proxy inverse et le serveur frontal ne doivent pas utiliser l’algorithme de hachage SHA-512.
  
La liste de révocation de certificats HTTP doit être définie et accessible par le client. Par exemple, nous ne prenons pas en charge une entrée LDAP dans le certificat en tant que liste de révocation de certificats.
  
### <a name="dns"></a>DNS

La mobilité doit être correctement déployée pour que le client Skype Entreprise sur Mac fonctionne correctement. Un scénario d’échec courant consiste à résoudre les deux entrées DNS suivantes sur le réseau interne :
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
Pour plus d’informations, voir : [Deploying Mobility in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility), and the [Microsoft Lync Server 2010 Mobility Guide](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Voir aussi
<a name="Infrastructure"> </a>

[Exigences relatives au DNS pour Skype Entreprise Server](../../plan-your-deployment/network-requirements/dns.md)

[Questions fréquemment posées](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Problèmes connus](https://go.microsoft.com/fwlink/p/?LinkId=798228)