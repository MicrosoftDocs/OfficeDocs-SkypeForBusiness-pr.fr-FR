---
title: Planification de la connexion hybride | Intégration de Skype entreprise Server 2019 Microsoft 365 et Office 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Considérations relatives à la planification de la mise en œuvre d’une connectivité hybride entre Skype entreprise Server et Skype entreprise Online ou Teams.
ms.openlocfilehash: ff0ac03d0f93eaa509badb4462d179b41f77ab21
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779751"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-microsoft-365-or-office-365"></a>Planification de la connectivité hybride entre Skype entreprise Server et Microsoft 365 ou Office 365

## <a name="overview"></a>Vue d’ensemble

Consultez cette rubrique pour découvrir comment planifier une connectivité hybride entre Skype entreprise Server et teams ou Skype entreprise online. La configuration de la connectivité hybride constitue la première étape de la migration de votre environnement local vers le Cloud.

Si vous avez des utilisateurs Skype Entreprise locaux qui utilisent également Teams (côte à côte), ces utilisateurs n’ont pas la possibilité d’interagir avec des utilisateurs de Skype Entreprise à partir de leur client Teams, ni de communiquer avec des utilisateurs d’organisations fédérées à partir de leur client Teams. Pour obtenir cette fonctionnalité dans Teams, ces utilisateurs doivent être déplacés de Skype Entreprise en local vers le Cloud, ce qui nécessite la configuration du mode hybride Skype Entreprise. En outre, pour une expérience optimale, ces utilisateurs doivent être en mode teams uniquement, ce qui garantit tous les appels entrants et les conversations provenant de n’importe quel utilisateur dans le client teams de l’utilisateur.

Vous devez également configurer la connectivité hybride et déplacer tous les utilisateurs vers le cloud avant de supprimer votre déploiement Skype Entreprise local.  Une fois la connectivité hybride configurée, vous pouvez choisir de migrer vos utilisateurs vers le cloud en fonction de votre planification et de vos besoins professionnels. Le routage direct vous permet de tirer parti de votre infrastructure vocale locale pendant votre migration vers le cloud et une fois celle-ci terminée.

Cette rubrique décrit la configuration requise pour l’infrastructure et le système, dont vous aurez besoin pour configurer une connectivité hybride entre votre déploiement Skype entreprise Server existant et teams ou Skype entreprise online.

Une fois que vous avez lu cette rubrique et que vous êtes prêt à configurer la connectivité hybride, reportez-vous à [configurer la connectivité hybride entre Skype entreprise Server et Office 365](configure-hybrid-connectivity.md). Les rubriques relatives à la configuration fournissent des instructions détaillées sur la configuration de la connectivité hybride entre votre déploiement local et teams ou Skype entreprise online.

## <a name="about-shared-sip-address-space-functionality"></a>À propos de la fonctionnalité d’espace d’adressage SIP partagé

<a name="BKMK_Overview"> </a>

 Avec la connectivité hybride définie entre un déploiement local de Skype entreprise Server et teams ou Skype entreprise Online, certains utilisateurs peuvent être hébergés en local et certains utilisateurs sont hébergés en ligne.

Ce type de configuration repose sur la fonctionnalité d’espace d’adressage SIP partagé, et est parfois appelé « domaine fractionné », ce qui signifie que les utilisateurs d’un domaine, comme contoso.com, sont répartis entre Skype entreprise Server sur site et teams ou Skype entreprise Online, comme illustré dans le diagramme suivant :

![Connectivité hybride SfB-domaine fractionné](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

En cas de configuration de l’espace d’adressage SIP partagé :

- Azure Active Directory Connect est utilisé pour synchroniser votre annuaire local avec Office 365.
- Les utilisateurs hébergés sur site interagissent avec les serveurs Skype entreprise locaux.
- Les utilisateurs hébergés en ligne peuvent interagir avec Skype entreprise Online ou Team Services.
- Les utilisateurs des deux environnements peuvent communiquer les uns avec les autres.
- Active Directory sur site fait autorité. Tous les utilisateurs doivent d’abord être créés dans Active Directory locale, puis synchronisés avec Azure AD. Même si vous souhaitez que l’utilisateur soit hébergé en ligne, vous devez d’abord créer l’utilisateur dans l’environnement local, puis déplacer l’utilisateur vers le service en ligne pour vous assurer que l’utilisateur peut être découvert par les utilisateurs locaux.

Pour qu’un utilisateur puisse être déplacé en ligne, une licence Skype entreprise Online (plan 2) doit être affectée à l’utilisateur. Si l’utilisateur doit utiliser Teams, vous devez lui attribuer une licence Teams (et la licence Skype entreprise doit rester activée). Si vos utilisateurs souhaitent tirer parti de fonctionnalités en ligne supplémentaires, telles que l’audioconférence ou le système téléphonique, vous devez leur attribuer la licence appropriée dans Office 365.

## <a name="infrastructure-requirements"></a>Conditions requises en matière d’infrastructure

<a name="BKMK_Infrastructure"> </a>

Pour implémenter une connectivité hybride entre votre environnement local et les services de communication Office 365, vous devez respecter les exigences d’infrastructure suivantes :

- Un seul déploiement local de Skype entreprise Server ou de Lync Server déployé dans une topologie prise en charge. Consultez la rubrique [Configuration requise](plan-hybrid-connectivity.md#BKMK_Topology) pour la topologie dans cette rubrique.
- Une organisation Microsoft Office 365 avec Skype entreprise Online activé.
    > [!NOTE]
    > Vous ne pouvez utiliser qu’un seul client pour une configuration hybride avec votre déploiement local.
- Azure Active Directory Connect pour synchroniser votre annuaire local avec Office 365. Pour plus d’informations, reportez-vous à la rubrique [Azure ad Connect : comptes et autorisations](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).
- Outils d’administration de Skype entreprise Server.  Ces éléments sont requis pour déplacer les utilisateurs de l’organisation locale vers le Cloud. Ces outils doivent être installés sur un serveur ayant accès à la fois au déploiement local et à Internet.
- Outils d’administration en ligne.  Vous pouvez utiliser le centre d’administration teams ou Windows PowerShell pour gérer teams et Skype entreprise online. Pour utiliser PowerShell pour gérer teams ou Skype entreprise Online, téléchargez et installez le connecteur Skype entreprise online.
- L’espace d’adressage SIP partagé doit être activé et votre déploiement local doit être configuré pour utiliser Office 365 en tant que fournisseur d’hébergement. Pour plus d’informations sur les étapes nécessaires à la configuration de la connectivité hybride, voir [configure Hybrid Connectivity](configure-hybrid-connectivity.md).

Après avoir configuré la connectivité hybride, vous pouvez déplacer des utilisateurs vers teams ou Skype entreprise online. Pour plus d’informations, voir [Move users from on-premises to teams](move-users-from-on-premises-to-teams.md) et [Move users from on premises to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).

## <a name="server-version-requirements"></a>Configuration requise pour la version du serveur

<a name="BKMK_Topology"> </a>

Pour configurer votre déploiement hybride avec **teams ou Skype entreprise Online**, vous devez disposer de l’une des topologies prises en charge suivantes :

- Un déploiement de Skype entreprise Server 2019 avec tous les serveurs exécutant Skype entreprise Server 2019.
- Un déploiement de Skype entreprise Server 2015 avec tous les serveurs exécutant Skype entreprise Server 2015.
- Un déploiement Lync Server 2013 avec tous les serveurs exécutant Lync Server 2013.  Toutefois, si la connectivité vocale hybride est requise, vous devez utiliser une topologie de version mixte, comme indiqué ci-dessous.
- Un déploiement avec au maximum 2 versions de serveur différentes, comme décrit ci-dessous :
  - Skype entreprise Server 2015 et Skype entreprise Server 2019
  - Lync Server 2013 et Skype entreprise Server 2019
  - Lync Server 2013 et Skype entreprise Server 2015

*Si la voix hybride est souhaitée dans n’importe quelle topologie*, le serveur Edge désigné comme serveur Edge de Fédération et le pool associé à la Fédération SIP doivent exécuter Skype entreprise 2015 ou une version ultérieure. Les utilisateurs peuvent rester sur un pool Lync 2013 s’il en existe un. Pour plus d’informations, reportez-vous à la rubrique [plan Phone System with PSTN Connectivity in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).

Les topologies suivantes qui incluent **Lync Server 2010 sont prises en charge avec Skype entreprise Online** pour la messagerie instantanée et les réunions.  Les topologies qui incluent **Lync Server 2010 ne sont pas prises en charge pour la voix hybride ou les équipes**.

- Un déploiement mixte Lync Server 2010 et Skype entreprise Server 2015
- Un déploiement mixte Lync Server 2010 et Lync Server 2013
- Un déploiement de Lync Server 2010 avec tous les serveurs exécutant Lync Server 2010 avec les mises à jour cumulatives les plus récentes.

Le serveur Edge de Fédération et le serveur du tronçon suivant du serveur Edge de Fédération doivent exécuter Lync Server 2010 avec les mises à jour cumulatives les plus récentes. Les outils d’administration de Skype entreprise Server 2015 ou Lync Server 2013 doivent être installés sur au moins un serveur ou une station de gestion.

## <a name="multi-forest-support"></a>Prise en charge des environnements multi-forêts

<a name="BKMK_MultiForest"> </a>

Microsoft prend en charge les types de scénarios hybrides à forêts multiples suivants :

- **Topologie de forêt de ressources.** Dans ce type de topologie, il existe une forêt qui héberge Skype entreprise Server (la forêt de ressources) et il existe une ou plusieurs forêts supplémentaires qui hébergent des identités de compte qui accèdent au serveur Skype entreprise dans la forêt de ressources. En règle générale, les utilisateurs peuvent accéder aux fonctionnalités de Skype entreprise dans une autre forêt si les conditions suivantes sont remplies :
  - Les utilisateurs sont correctement synchronisés avec la forêt qui héberge Skype entreprise. Dans les configurations hybrides, cela signifie que les utilisateurs doivent être synchronisés en tant qu’objets utilisateur désactivés.
  - La forêt hébergeant Skype entreprise doit approuver la forêt contenant les utilisateurs.
    Pour plus d’informations sur les scénarios hybrides de forêt de ressources, voir [Deploy a Resource Forest Topology for Hybrid Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).
- **Plusieurs déploiements de Skype entreprise Server dans plusieurs forêts.** Cette configuration peut se produire à la suite de scénarios de fusion et d’acquisition, ainsi que dans les entreprises plus complexes.  La consolidation de tous les utilisateurs de local en nuage dans une organisation Office 365 unique peut être réalisée pour n’importe quelle organisation avec plusieurs déploiements Skype entreprise, à condition que les exigences clés suivantes soient respectées :

  - Il doit y avoir au plus une organisation Office 365 concernée. La consolidation dans des scénarios avec plus d’une organisation Office 365 n’est pas prise en charge.
  - À un moment donné, une seule forêt Skype entreprise locale peut être en mode hybride (espace d’adressage SIP partagé). Toutes les autres forêts Skype entreprise locales doivent rester entièrement locales (et mutuellement fédérées les unes avec les autres). Notez que ces autres organisations locales peuvent effectuer une synchronisation avec AAD si vous le souhaitez avec de [nouvelles fonctionnalités pour désactiver les domaines SIP en ligne](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) disponibles à partir du 2018 décembre.

    Les clients avec des déploiements de Skype entreprise dans plusieurs forêts doivent totalement migrer chaque forêt Skype entreprise de manière individuelle vers l’organisation Office 365 à l’aide de la fonctionnalité espace d’adressage SIP partagé, puis désactiver hybride avec le déploiement local, avant de passer à la migration du déploiement Skype entreprise suivant. Par ailleurs, avant d’être migrés vers le Cloud, les utilisateurs locaux restent dans un État fédéré avec tous les utilisateurs qui ne sont pas représentés dans le même annuaire local de l’utilisateur. Pour plus d’informations, consultez la rubrique [consolidation du Cloud pour teams et Skype entreprise](cloud-consolidation.md).

## <a name="federation-requirements"></a>Conditions requises pour la Fédération

<a name="BKMK_Federation"> </a>

Lors de la configuration d’un environnement hybride, vous devez vous assurer que vos environnements locaux et en ligne peuvent se fédérer les uns avec les autres.  L’environnement en ligne est doté d’une Fédération ouverte par défaut ; dans l’environnement local, la Fédération est souvent fermée par défaut.  

Les conditions requises suivantes doivent être remplies pour pouvoir configurer un déploiement hybride :

- La correspondance de domaine doit être configurée de la même façon pour votre déploiement local et votre organisation Office 365. Si la découverte des partenaires est activée sur le déploiement local, la Fédération ouverte doit être configurée pour votre client en ligne. Si la découverte de partenaire n’est pas activée, alors la Fédération fermée doit être configurée pour votre client en ligne.
- La liste des domaines bloqués dans le déploiement local doit correspondre exactement à la liste des domaines bloqués pour votre client en ligne.
- La liste des domaines autorisés dans le déploiement local doit correspondre exactement à la liste des domaines autorisés pour votre client en ligne.
- La Fédération doit être activée pour les communications externes pour le client en ligne.

## <a name="network-considerations"></a>Considérations relatives au réseau

Les sections suivantes décrivent les points à prendre en compte pour :

- Paramètres DNS
- Considérations relatives au pare-feu

### <a name="dns-settings"></a>Paramètres DNS

<a name="BKMK_DNS"> </a>

Lors de la création d’enregistrements DNS pour les déploiements hybrides, tous les enregistrements DNS externes de Skype entreprise doivent pointer vers l’infrastructure locale. Pour plus d’informations sur les enregistrements DNS requis, reportez-vous à la rubrique [DNS Requirements for Skype for Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

En outre, vous devez vous assurer que la résolution DNS décrite dans le tableau suivant fonctionne dans votre déploiement local. (Si vous avez déjà configuré la Fédération sur site, vous en aurez probablement déjà un.)

|Enregistrement DNS  <br/> |Résolu par  <br/> |Enregistrement DNS requis  <br/> |
|:-----|:-----|:-----|
|Enregistrement DNS SRV pour _sipfederationtls. _tcp. \<sipdomain.com\> pour tous les domaines SIP pris en charge résolus pour accéder à l’adresse IP externe du serveur Edge (s)  <br/> |Serveur (s) Edge  <br/> |Activer la communication fédérée dans une configuration hybride. Le serveur Edge doit indiquer où acheminer le trafic fédéré pour le domaine SIP qui est réparti entre local et en ligne.  <br/> Doit utiliser une correspondance de nom DNS stricte entre le domaine dans le nom d’utilisateur et l’enregistrement SRV.  <br/> |
|Enregistrements DNS A (s) pour le nom de domaine complet du service de conférence Web Edge, par exemple webcon.contoso.com résolution des adresses IP externes Edge de conférence Web  <br/> |Ordinateurs des utilisateurs connectés au réseau d’entreprise interne  <br/> |Permettre aux utilisateurs en ligne de présenter ou d’afficher le contenu des réunions hébergées sur site. Le contenu inclut des fichiers PowerPoint, des tableaux blancs, des sondages et des notes partagées.  <br/> |

En fonction de la configuration de DNS dans votre organisation, il se peut que vous deviez ajouter ces enregistrements à la zone DNS hébergée interne pour les domaines SIP correspondants afin de fournir la résolution DNS interne à ces enregistrements.

### <a name="firewall-considerations"></a>Considérations relatives au pare-feu

<a name="BKMK_Firewall"> </a>

Les ordinateurs de votre réseau doivent être en mesure d’effectuer des recherches DNS Internet standard. Si ces ordinateurs peuvent accéder à des sites Internet standard, votre réseau répond à cette exigence.

En fonction de l’emplacement de votre centre de données Microsoft Online Services, vous devez également configurer vos périphériques de pare-feu réseau pour qu’ils acceptent les connexions basées sur des noms de \*domaine génériques (par exemple, tout le trafic provenant de. Outlook.com). Si les pare-feu de votre organisation ne prennent pas en charge les configurations de nom génériques, vous devrez déterminer manuellement les plages d’adresses IP que vous voulez autoriser et les ports spécifiés.

Pour plus d’informations, notamment des détails sur les ports et les protocoles requis, voir [URL et plages d’adresses IP Office 365](https://go.microsoft.com/fwlink/p/?LinkId=252942).
