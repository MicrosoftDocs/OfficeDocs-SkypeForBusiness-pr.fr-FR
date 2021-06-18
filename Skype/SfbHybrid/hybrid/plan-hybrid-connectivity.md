---
title: Planifier la connexion hybride | Intégration de Skype Entreprise Server 2019 et Microsoft 365 ou Office 365
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
description: Prévoyez d’implémenter la connectivité hybride entre Skype Entreprise Server et Teams ou Skype Entreprise Online en configurant le mode hybride Skype Entreprise.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 1a43243f4b5ce827a7c688c1aad1983466aa6ca7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110260"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-microsoft-365-or-office-365"></a> Planifier une connectivité hybride entre Skype pour serveur d'entreprise et Microsoft 365 ou Office 365

Lisez cette rubrique pour découvrir comment planifier la connectivité hybride entre Skype Entreprise Server et Teams ou Skype Entreprise Online. La configuration de la connectivité hybride constitue la première étape de la migration de votre environnement local vers le Cloud.

Si vous avez des utilisateurs Skype Entreprise locaux qui utilisent également Teams (côte à côte), ces utilisateurs n’ont pas la possibilité d’interagir avec des utilisateurs de Skype Entreprise à partir de leur client Teams, ni de communiquer avec des utilisateurs d’organisations fédérées à partir de leur client Teams. Pour obtenir cette fonctionnalité dans Teams, ces utilisateurs doivent être déplacés de Skype Entreprise en local vers le Cloud, ce qui nécessite la configuration du mode hybride Skype Entreprise. En outre, pour une expérience de qualité, ces utilisateurs doivent être en mode Teams uniquement, ce qui garantit que tous les appels entrants et conversations de n’importe quel utilisateur arrivent dans le client Teams de l’utilisateur.

Vous devez également configurer la connectivité hybride et déplacer tous les utilisateurs vers le cloud avant de supprimer votre déploiement Skype Entreprise local.  Une fois la connectivité hybride configurée, vous pouvez choisir de migrer vos utilisateurs vers le cloud en fonction de votre planification et de vos besoins professionnels. Le routage direct vous permet de tirer parti de votre infrastructure vocale locale pendant votre migration vers le cloud et une fois celle-ci terminée.

Cette rubrique décrit l’infrastructure et la configuration système requises pour configurer la connectivité hybride entre votre déploiement Skype Entreprise Server local existant et Teams ou Skype Entreprise Online.

Une fois que vous avez lu cette rubrique et que vous êtes prêt à configurer la connectivité hybride, voir Configurer la connectivité hybride entre Skype Entreprise Server et [Microsoft 365 ou Office 365.](configure-hybrid-connectivity.md) Les rubriques de configuration fournissent des instructions pas à pas pour la configuration de la connectivité hybride entre votre déploiement local et Teams ou Skype Entreprise Online.

> [!Important]
> Skype Entreprise Online sera retiré le 31 juillet 2021, après quoi le service ne sera plus accessible.  En outre, la connectivité PSTN entre votre environnement local via Skype Entreprise Server ou Cloud Connector Edition et Skype Entreprise Online ne sera plus prise en charge.  Découvrez comment connecter votre réseau téléphonique local à Teams à l’aide [du routage direct.](/MicrosoftTeams/direct-routing-landing-page)

## <a name="about-shared-sip-address-space-functionality"></a>À propos de la fonctionnalité d’espace d’adressas SIP partagé

<a name="BKMK_Overview"> </a>

 Avec la connectivité hybride définie entre un déploiement local de Skype Entreprise Server et Teams ou Skype Entreprise Online, vous pouvez avoir certains utilisateurs sur site et d’autres en ligne.

Ce type de configuration s’appuie sur la fonctionnalité d’espace d’adressamage SIP partagé et est parfois appelé « domaine fractioné », c’est-à-dire que les utilisateurs d’un domaine, tels que contoso.com, sont répartis entre l’utilisation de Skype Entreprise Server sur site et Teams ou Skype Entreprise Online, comme illustré dans le diagramme suivant :

![Connectivité hybride Skype Entreprise - domaine fractioné](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Lorsque l’espace d’adressas SIP partagé est configuré :

- Azure Active Directory Connect est utilisé pour synchroniser votre annuaire local avec Microsoft 365 ou Office 365.
- Les utilisateurs qui sont locaux interagissent avec les serveurs Skype Entreprise locaux.
- Les utilisateurs qui sont en ligne peuvent interagir avec les services Skype Entreprise Online ou Teams.
- Les utilisateurs des deux environnements peuvent communiquer les uns avec les autres.
- Active Directory local fait autorité. Tous les utilisateurs doivent d’abord être créés dans l’annuaire Active Directory local, puis synchronisés avec Azure AD. Même si vous souhaitez que l’utilisateur soit homed online, vous devez d’abord créer l’utilisateur dans l’environnement local, puis le déplacer en ligne pour vous assurer que l’utilisateur est découvrable par les utilisateurs locaux.

Pour qu’un utilisateur puisse être déplacé en ligne, une licence Skype Entreprise Online (Plan 2) doit lui être attribuée. Si l’utilisateur utilise Teams, il doit également se voir attribuer une licence Teams (et la licence Skype Entreprise doit rester activée). Si vos utilisateurs souhaitent tirer parti de fonctionnalités en ligne supplémentaires, telles que l’audioconférence ou le système téléphonique, vous devez leur attribuer la licence appropriée dans Microsoft 365 ou Office 365.

## <a name="hybrid-connectivity-infrastructure-requirements"></a>Exigences relatives à l’infrastructure de connectivité hybride

<a name="BKMK_Infrastructure"> </a>

Pour implémenter la connectivité hybride entre votre environnement local et les services de communication Microsoft 365 ou Office 365, vous devez respecter les exigences d’infrastructure suivantes :

- Déploiement local unique de Skype Entreprise Server ou de Lync Server déployé dans une topologie prise en charge. Voir [la topologie requise](plan-hybrid-connectivity.md#BKMK_Topology) dans cette rubrique.

- Une organisation Microsoft 365 ou Office 365 avec Skype Entreprise Online activé.
    > [!NOTE]
    > Vous ne pouvez utiliser qu’un seul client pour une configuration hybride avec votre déploiement local.
    
- Azure Active Directory Connect pour synchroniser votre annuaire local avec Microsoft 365 ou Office 365. Pour plus d’informations, [voir Azure AD Connect : Comptes et autorisations.](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)

- Outils d’administration Skype Entreprise Server. Ceux-ci sont nécessaires pour déplacer des utilisateurs de l’local vers le cloud. Ces outils doivent être installés sur un serveur ayant accès à la fois au déploiement local et à Internet.
- Outils d’administration en ligne. Vous pouvez utiliser le Centre d’administration Teams ou Windows PowerShell pour gérer Teams et Skype Entreprise Online. Pour utiliser PowerShell afin de gérer Teams ou Skype Entreprise Online, téléchargez et installez le connecteur Skype Entreprise Online.
- L’espace d’adressare SIP partagé doit être activé et votre déploiement local doit être configuré pour utiliser Microsoft 365 ou Office 365 en tant que fournisseur d’hébergement. Pour plus d’informations sur les étapes requises pour configurer la connectivité hybride, voir [Configurer la connectivité hybride.](configure-hybrid-connectivity.md)

Après avoir configuré la connectivité hybride, vous pouvez déplacer des utilisateurs vers Teams ou Skype Entreprise Online. Pour plus d’informations, voir [Move users from on-premises to Teams](move-users-from-on-premises-to-teams.md) and Move users from on [premises to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).

## <a name="server-version-requirements"></a>Conditions requises pour la version du serveur

<a name="BKMK_Topology"> </a>

Pour configurer votre déploiement hybride avec Teams ou **Skype Entreprise Online,** vous devez avoir l’une des topologies suivantes :

- Déploiement de Skype Entreprise Server 2019 avec tous les serveurs exécutant Skype Entreprise Server 2019.
- Déploiement de Skype Entreprise Server 2015 avec tous les serveurs exécutant Skype Entreprise Server 2015.
- Un déploiement Lync Server 2013 avec tous les serveurs exécutant Lync Server 2013.  Toutefois, si la connectivité vocale hybride est requise, vous devez utiliser une topologie de version mixte comme indiqué ci-dessous.
- Un déploiement avec un maximum de 2 versions de serveur différentes, comme répertorié ci-dessous :
  - Skype Entreprise Server 2015 et Skype Entreprise Server 2019
  - Lync Server 2013 et Skype Entreprise Server 2019
  - Lync Server 2013 et Skype Entreprise Server 2015

Si la voix hybride est souhaitée dans une topologie, le serveur Edge désigné comme serveur Edge de fédération ainsi que le pool associé à la fédération SIP doivent tous deux utiliser Skype Entreprise 2015 ou une version ultérieure. Les utilisateurs peuvent rester sur un pool Lync 2013 s’il en existe un. Pour plus d’informations, voir [Plan Phone System with PSTN Connectivity in Skype for Business Server](../../SfbServer/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).

Les topologies suivantes qui incluent **Lync Server 2010** sont pris en charge avec Skype Entreprise Online pour la messagerie instantanée et les réunions. Les topologies qui incluent **Lync Server 2010** ne sont pas pris en charge pour la voix hybride ni teams.

- Déploiement mixte de Lync Server 2010 et Skype Entreprise Server 2015
- Déploiement mixte de Lync Server 2010 et Lync Server 2013
- Un déploiement Lync Server 2010 avec tous les serveurs exécutant Lync Server 2010 avec les dernières mises à jour cumulatives.

Le serveur Edge de fédération et le serveur du saut suivant du serveur Edge de fédération doivent exécutent Lync Server 2010 avec les dernières mises à jour cumulatives. Les outils d’administration Skype Entreprise Server 2015 ou Lync Server 2013 doivent être installés sur au moins un serveur ou une station de travail de gestion.

## <a name="multi-forest-support"></a>Prise en charge des environnements multi-forêts

<a name="BKMK_MultiForest"> </a>

Microsoft prend en charge les types de scénarios hybrides à forêts multiples suivants :

- **Topologie de forêt ressource.** Dans ce type de topologie, il existe une forêt qui héberge Skype Entreprise Server (la forêt de ressources), et il existe une ou plusieurs forêts supplémentaires qui hébergent des identités de compte, qui accèdent à Skype Entreprise Server dans la forêt de ressources. En règle générale, les utilisateurs peuvent accéder aux fonctionnalités de Skype Entreprise dans une autre forêt si les conditions suivantes sont remplies :
  - Les utilisateurs sont correctement synchronisés dans la forêt qui héberge Skype Entreprise. Dans les configurations hybrides, cela signifie que les utilisateurs doivent être synchronisés en tant qu’objets utilisateur désactivés.
  - La forêt qui héberge Skype Entreprise doit faire confiance à la forêt contenant les utilisateurs.
    Pour plus d’informations sur les scénarios hybrides de forêt de ressources, voir [Deploy a resource forest topology for hybrid Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).

- **Plusieurs déploiements de Skype Entreprise Server dans plusieurs forêts.** Cette configuration peut survenir suite à des scénarios de fusion et d’acquisition, ainsi que dans des entreprises plus complexes. La consolidation de tous les utilisateurs locaux vers le cloud dans une seule organisation Microsoft 365 ou Office 365 peut être réalisée pour n’importe quelle organisation avec plusieurs déploiements Skype Entreprise, à condition que les conditions clés suivantes soient remplies :
  - Au maximum une organisation Microsoft 365 ou Office 365 doit être impliquée. La consolidation dans les scénarios avec plusieurs organisations n’est pas prise en charge.
  - À tout moment, une seule forêt Skype Entreprise sur site peut être en mode hybride (espace d’adressace SIP partagé). Toutes les autres forêts Skype Entreprise sur site doivent rester entièrement en local (et probablement fédérées les unes avec les autres). Notez que ces autres organisations locales peuvent se synchroniser avec AAD si vous le souhaitez avec de nouvelles fonctionnalités pour désactiver les domaines [SIP](/powershell/module/skype/disable-csonlinesipdomain) en ligne disponibles à partir de décembre 2018.

    Les clients avec des déploiements de Skype Entreprise dans plusieurs forêts doivent migrer entièrement chaque forêt Skype Entreprise individuellement vers l’organisation Microsoft 365 ou Office 365 à l’aide de la fonctionnalité de domaine partagé (espace d’adressare SIP partagé), puis désactiver l’hybride avec le déploiement local, avant de migrer le déploiement skype entreprise local suivant. En outre, avant d’être migrés vers le cloud, les utilisateurs locaux restent dans un état fédéré avec tous les utilisateurs qui ne sont pas représentés dans l’annuaire local du même utilisateur. Pour plus d’informations, voir [Consolidation cloud pour Teams et Skype Entreprise.](cloud-consolidation.md)

## <a name="federation-requirements"></a>Conditions requises pour la fédération

<a name="BKMK_Federation"> </a>

Lors de la configuration du mode hybride Skype Entreprise, vous devez vous assurer que vos environnements locaux et en ligne peuvent se fédérer les uns avec les autres.  L’environnement en ligne dispose d’une fédération ouverte par défaut . L’environnement local a souvent fermé la fédération par défaut.  

Les conditions suivantes doivent être remplies pour configurer correctement un déploiement hybride :

- La correspondance de domaine doit être configurée de la même manière pour votre déploiement local et votre organisation Microsoft 365 ou Office 365. Si la découverte des partenaires est activée sur le déploiement local, la fédération ouverte doit être configurée pour votre organisation en ligne. Si la découverte des partenaires n’est pas activée, la fédération fermée doit être configurée pour votre organisation en ligne.
- La liste des domaines bloqués dans le déploiement local doit correspondre exactement à la liste des domaines bloqués de votre client en ligne.
- La liste des domaines autorisés dans le déploiement local doit correspondre exactement à la liste des domaines autorisés pour votre client en ligne.
- La fédération doit être activée pour les communications externes pour le client en ligne.

## <a name="network-considerations"></a>Considérations relatives au réseau

Les sections suivantes décrivent les éléments à prendre en compte :

- Paramètres DNS
- Considérations sur le pare-feu

### <a name="dns-settings-for-hybrid-deployments"></a>Paramètres DNS pour les déploiements hybrides

<a name="BKMK_DNS"> </a>

Lors de la création d’enregistrements DNS pour des déploiements hybrides, tous les enregistrements DNS externes Skype Entreprise doivent pointer vers l’infrastructure locale. Pour plus d’informations sur les enregistrements DNS requis, reportez-vous aux exigences [DNS pour Skype Entreprise Server.](../../sfbserver/plan-your-deployment/network-requirements/dns.md)

En outre, vous devez vous assurer que la résolution DNS décrite dans le tableau suivant fonctionne dans votre déploiement local. (Si vous avez déjà configuré la fédération pour l’local, vous en avez probablement déjà.)

|Enregistrement DNS  <br/> |Résolvable par  <br/> |Enregistrement DNS requis  <br/> |
|:-----|:-----|:-----|
|Enregistrement DNS SRV pour _sipfederationtls._tcp.\<sipdomain.com\> pour tous les domaines SIP pris en charge résolvant les adresses IP externes du edge d’accès  <br/> |Serveurs Edge  <br/> |Activer la communication fédérée dans une configuration hybride. Le serveur Edge doit savoir où router le trafic fédéré pour le domaine SIP qui est réparti entre le trafic local et en ligne.  <br/> Doit utiliser une correspondance stricte de nom DNS entre le domaine dans le nom d’utilisateur et l’enregistrement SRV.  <br/> |
|DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)  <br/> |Ordinateurs des utilisateurs connectés au réseau d’entreprise interne  <br/> |Permettre aux utilisateurs en ligne de présenter ou d’afficher du contenu dans des réunions hébergées sur site. Le contenu inclut des fichiers PowerPoint, des tableaux blancs, des sondages et des notes partagées.  <br/> |

Selon la configuration du DNS dans votre organisation, vous devrez peut-être ajouter ces enregistrements à la zone DNS hébergée interne pour le ou les domaines SIP correspondants afin de fournir une résolution DNS interne à ces enregistrements.

### <a name="firewall-considerations-for-hybrid-deployments"></a>Considérations sur le pare-feu pour les déploiements hybrides

<a name="BKMK_Firewall"> </a>

Les ordinateurs de votre réseau doivent pouvoir effectuer des recherche DNS Internet standard. Si ces ordinateurs peuvent accéder à des sites Internet standard, votre réseau répond à cette exigence.

Selon l’emplacement de votre centre de données Microsoft Online Services, vous devez également configurer vos périphériques de pare-feu réseau pour accepter les connexions basées sur des noms de domaine génériques (par exemple, tout le trafic en provenance de \* .outlook.com). Si les pare-feu de votre organisation ne permettent pas la configuration des noms génériques, vous devez déterminer manuellement les plages d’adresses IP que vous souhaitez autoriser et les ports spécifiés.

Pour plus d’informations, notamment sur les ports et les protocoles requis, voir URL et [plages d’adresses IP Microsoft 365 et Office 365.](/microsoft-365/enterprise/urls-and-ip-address-ranges)