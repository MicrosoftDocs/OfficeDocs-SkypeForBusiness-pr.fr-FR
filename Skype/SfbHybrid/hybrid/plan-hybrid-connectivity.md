---
title: Planifier la connectivité hybride | Skype Entreprise Server et Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Prévoyez d’implémenter la connectivité hybride entre Skype Entreprise Server et Teams en configurant Skype Entreprise mode hybride.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: c1faef42d6c5842649bfb8b8bf79531ac2e367b0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58600879"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Planifier la connectivité hybride entre Skype Entreprise Server et Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Lisez cette rubrique pour découvrir comment planifier la connectivité hybride entre Skype Entreprise Server et Teams. La configuration de la connectivité hybride constitue la première étape de la migration de votre environnement local vers le Cloud.

Si vous avez des utilisateurs Skype Entreprise locaux qui utilisent également Teams (côte à côte), ces utilisateurs n’ont pas la possibilité d’interagir avec des utilisateurs de Skype Entreprise à partir de leur client Teams, ni de communiquer avec des utilisateurs d’organisations fédérées à partir de leur client Teams. Pour obtenir cette fonctionnalité dans Teams, ces utilisateurs doivent être déplacés de Skype Entreprise en local vers le Cloud, ce qui nécessite la configuration du mode hybride Skype Entreprise. En outre, pour une expérience de qualité, ces utilisateurs doivent être en mode Teams Uniquement, ce qui garantit que tous les appels entrants et conversations de tout utilisateur arrivent dans le client Teams de l’utilisateur.

Vous devez également configurer la connectivité hybride et déplacer tous les utilisateurs vers le cloud avant de supprimer votre déploiement Skype Entreprise local.  Une fois la connectivité hybride configurée, vous pouvez choisir de migrer vos utilisateurs vers le cloud en fonction de votre planification et de vos besoins professionnels. Le routage direct vous permet de tirer parti de votre infrastructure vocale locale pendant votre migration vers le cloud et une fois celle-ci terminée.

Cette rubrique décrit l’infrastructure et la configuration système requises pour configurer la connectivité hybride entre votre déploiement local Skype Entreprise Server et votre Teams.

Une fois que vous avez lu cette rubrique et que vous êtes prêt à configurer la connectivité hybride, voir Configurer la connectivité hybride entre Skype Entreprise Server [et Teams](configure-hybrid-connectivity.md). Les rubriques de configuration fournissent des instructions pas à pas pour la configuration de la connectivité hybride entre votre déploiement local et Teams.

> [!Important]
> Skype Entreprise Online sera retiré le 31 juillet 2021, après quoi le service ne sera plus accessible.  En outre, la connectivité PSTN entre votre environnement local via Skype Entreprise Server ou Cloud Connector Edition et Skype Entreprise Online ne sera plus prise en charge.  Découvrez comment connecter votre réseau téléphonique local à Teams l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)

## <a name="implications-of-the-upcoming-retirement-of-skype-for-business-online"></a>Implications du retrait à venir de Skype Entreprise Online
Il est important de se souvenir qu’avant et après le retrait de Skype Entreprise Online, les utilisateurs Skype Entreprise Server sur site peuvent utiliser Teams, mais ils ne peuvent pas être TeamsOnly. (Par défaut, les utilisateurs sont en mode Îles). Les utilisateurs peuvent uniquement profiter des avantages complets de Teams, en particulier la fédération et la prise en charge PSTN, une fois qu’ils sont en mode TeamsOnly. 

Le retrait à venir de Skype Entreprise Online n’a aucun impact sur le cycle de vie de support existant de Skype Entreprise Server ou Lync Server 2013.  Toutefois, le retrait à venir de Skype Entreprise Online aura un impact sur certains aspects de la transition des clients avec Skype Entreprise Server local ou Lync Server 2013, y compris les organisations hybrides existantes, vers le cloud. Ce qui ne change pas après le retrait, c’est que l’utilisation de l’hybride comme moyen de transition de l’local vers le cloud reste inchangée.

Actuellement, et jusqu’au retrait de Skype Entreprise Online, les organisations hybrides peuvent se composer de trois types d’utilisateurs de base : 
- Utilisateurs locaux (qui peuvent ou ne peuvent pas utiliser Teams, mais pas en mode Teams uniquement) 
- Utilisateurs en ligne avec tout mode de coexistence autre que TeamsOnly
- Utilisateurs TeamsOnly.

Après le retrait de Skype Entreprise Online, toutefois, les organisations hybrides ne peuvent être constituées que de deux types d’utilisateurs de base : 
- Les utilisateurs locaux (Qui peuvent ou non utiliser Teams, mais pas en mode TeamsOnly)
- Teams Utilisateurs uniquement. 

Pour que les organisations passeront de Skype Entreprise Server ou Lync Server 2013 à Teams, elles doivent quand même configurer l’hybride à l’aide du même ensemble d’outils, exactement comme avant le retrait. Ce qui a changé, c’est que lors du déplacement d’un utilisateur de l’local vers Teams, il n’est plus nécessaire de spécifier le commutateur pour déplacer les utilisateurs directement de l’local vers `-MoveToTeams` `Move-CsUser` TeamsOnly. Auparavant, si ce commutateur n’était pas spécifié, les utilisateurs passaient du mode d’accueil Skype Entreprise Server local à Skype Entreprise Online, et leur mode était inchangé. En prévision du retrait, lors du déplacement d’un utilisateur de l’local vers le cloud avec , les utilisateurs sont désormais automatiquement affectés au mode TeamsOnly et leurs réunions à partir de l’local sont automatiquement converties en réunions Teams, comme si le commutateur avait été spécifié, que le commutateur soit réellement spécifié `Move-CsUser` `-MoveToTeams` ou non. (Cela inclut les migrations de Lync Server 2013, qui n’ont jamais eu le `MoveToTeams` commutateur.) 

De même, si un nouvel utilisateur est créé directement dans Microsoft 365 plutôt que sur site, il aura automatiquement le mode Teams Uniquement quel que soit le mode du client. (Ce comportement sera prochainement déployé avec le retrait.) N’oubliez pas que dans une organisation hybride, les nouveaux utilisateurs doivent être créés dans Active Directory local (puis synchronisés dans Microsoft 365), plutôt que de créer directement un utilisateur dans Microsoft 365, afin de s’assurer que les utilisateurs locaux peuvent router vers le nouvel utilisateur.

Les modes de coexistence continueront d’exister après le retrait de Skype Entreprise Online. Comme auparavant, les utilisateurs ayant des comptes Skype Entreprise Server sur site peuvent se voir attribuer n’importe quel mode de coexistence à l’exception de TeamsOnly. Toutefois, après la mise en retrait, les utilisateurs d’accueil en ligne peuvent uniquement être TeamsOnly (contrairement au moment où les utilisateurs Skype Entreprise Online peuvent être n’importe quel mode).  

> [!Important]
> - Les organisations hybrides existantes avec des utilisateurs Skype Entreprise Online qui ne sont PAS TeamsOnly doivent se concentrer sur la mise à niveau de ces utilisateurs vers le mode Teams Uniquement dès que possible, mais au plus tard le 31 juillet 2021. Si les utilisateurs de votre organisation sont toujours Skype Entreprise Online qui ne sont pas TeamsOnly, vous pouvez être programmé pour une mise à niveau assistée par Microsoft pour la transition de ces utilisateurs vers TeamsOnly. Cela n’aura aucun impact sur les utilisateurs qui sont Skype Entreprise Server sur site. Les notifications de planification seront envoyées à l’avance aux clients hybrides dont les utilisateurs sont Skype Entreprise Online avant que ces utilisateurs en ligne ne soient mis à niveau vers Teams.
> - En vue du retrait de Skype Entreprise Online, il ne sera bientôt plus possible d’affecter un mode autre que TeamsOnly à un utilisateur qui est en ligne.

## <a name="about-shared-sip-address-space-functionality"></a>À propos de la fonctionnalité d’espace d’adressas SIP partagé

<a name="BKMK_Overview"> </a>

 Avec la connectivité hybride définie entre un déploiement local de Skype Entreprise Server et Teams, vous pouvez avoir certains utilisateurs sur site et d’autres en ligne.

Ce type de configuration s’appuie sur la fonctionnalité d’espace d’adressare SIP partagé et est parfois appelé « domaine fractioné », c’est-à-dire que les utilisateurs d’un domaine, tels que contoso.com, sont répartis entre l’utilisation de Skype Entreprise Server en local et de Teams, comme illustré dans le diagramme suivant :

![Skype Entreprise hybride -domaine fractioné](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Lorsque l’espace d’adressas SIP partagé est configuré :

- Azure Active Directory Connecter permet de synchroniser votre annuaire local avec les Microsoft 365.
- Les utilisateurs qui sont sur site interagissent avec les serveurs Skype Entreprise locaux.
- Les utilisateurs qui sont basés en ligne peuvent interagir avec Teams et, jusqu’au 31 juillet 2021, Skype Entreprise Online en fonction de leur mode de coexistence.
- Les utilisateurs des deux environnements peuvent communiquer les uns avec les autres.
- Active Directory local fait autorité. Tous les utilisateurs doivent d’abord être créés dans l’annuaire Active Directory local, puis synchronisés avec Azure AD. Même si vous prévoyez d’installer l’utilisateur en ligne, vous devez d’abord créer l’utilisateur dans l’environnement local, puis le déplacer en ligne pour vous assurer que l’utilisateur est découvrable par les utilisateurs locaux.

Pour qu’un utilisateur puisse être déplacé en ligne, il doit se voir attribuer une licence Teams, ainsi que Skype Entreprise Online (Plan 2). **L’attribution de la licence Skype Entreprise Online est requise même après le retrait de Skype Entreprise Online.** Si vos utilisateurs souhaitent tirer parti de fonctionnalités en ligne supplémentaires, telles que l’audioconférence ou les Système téléphonique, vous devez leur attribuer la licence appropriée dans Microsoft 365.

## <a name="hybrid-connectivity-infrastructure-requirements"></a>Exigences relatives à l’infrastructure de connectivité hybride

<a name="BKMK_Infrastructure"> </a>

Pour implémenter la connectivité hybride entre votre environnement local et les services de communication Microsoft 365, vous devez respecter les exigences d’infrastructure suivantes :

- Déploiement local unique de Skype Entreprise Server ou Lync Server déployé dans une topologie prise en charge. Voir [la topologie requise](plan-hybrid-connectivity.md#BKMK_Topology) dans cette rubrique.

- Une Microsoft 365 organisation avec des Teams.
    > [!NOTE]
    > Vous ne pouvez utiliser qu’un seul client pour une configuration hybride avec votre déploiement local.
    
- Azure Active Directory Connecter synchroniser votre annuaire local avec les Microsoft 365. Pour plus d’informations, [voir Azure AD Connecter : Comptes et autorisations.](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)

- Skype Entreprise Server d’administration. Ceux-ci sont nécessaires pour déplacer des utilisateurs de l’local vers le cloud. Ces outils doivent être installés sur un serveur ayant accès à la fois au déploiement local et à Internet.
- Outils d’administration en ligne. Vous pouvez utiliser le Centre d’administration Teams ou Windows PowerShell pour gérer les Teams. Pour utiliser PowerShell afin de gérer les Teams, téléchargez et installez Teams module PowerShell. (Le connecteur Skype Entreprise Online Connector a été retiré).
- L’espace d’adressan SIP partagé doit être activé et votre déploiement local doit être configuré pour utiliser Microsoft 365 en tant que fournisseur d’hébergement. Pour plus d’informations sur les étapes requises pour configurer la connectivité hybride, voir [Configurer la connectivité hybride.](configure-hybrid-connectivity.md)

Après avoir configuré la connectivité hybride, vous pouvez déplacer les utilisateurs vers Teams. Pour plus d’informations, voir [Move users from on-premises to Teams](move-users-from-on-premises-to-teams.md).

## <a name="server-version-requirements"></a>Conditions requises pour la version du serveur

<a name="BKMK_Topology"> </a>

Pour configurer votre déploiement hybride avec **Teams,** vous devez avoir l’une des topologies suivantes :

- Déploiement de Skype Entreprise Server 2019 avec tous les serveurs exécutant Skype Entreprise Server 2019.
- Déploiement de Skype Entreprise Server 2015 avec tous les serveurs exécutant Skype Entreprise Server 2015.
- Un déploiement Lync Server 2013 avec tous les serveurs exécutant Lync Server 2013.  Toutefois, si la connectivité vocale hybride est requise, vous devez utiliser une topologie de version mixte comme indiqué ci-dessous.
- Un déploiement avec un maximum de 2 versions de serveur différentes, comme répertorié ci-dessous :
  - Skype Entreprise Server 2015 et Skype Entreprise Server 2019
  - Lync Server 2013 et Skype Entreprise Server 2019
  - Lync Server 2013 et Skype Entreprise Server 2015

Si la voix hybride est souhaitée dans une topologie, le serveur Edge désigné comme serveur Edge de fédération ainsi que le pool associé à la fédération SIP doivent être en cours d’exécution Skype Entreprise 2015 ou version ultérieure. Les utilisateurs peuvent rester sur un pool Lync 2013 s’il en existe un. Pour plus d’informations, voir [Planifier votre solution vocale.](/MicrosoftTeams/cloud-voice-landing-page.md)

> [!NOTE]
> Lync Server 2010 n’est pas pris en charge avec Teams.

## <a name="multi-forest-support"></a>Prise en charge des environnements multi-forêts

<a name="BKMK_MultiForest"> </a>

Microsoft prend en charge les types de scénarios hybrides à forêts multiples suivants :

- **Topologie de forêt ressource.** Dans ce type de topologie, il existe une forêt qui héberge Skype Entreprise Server (la forêt de ressources), et il existe une ou plusieurs forêts supplémentaires qui hébergent des identités de compte, qui accèdent au Skype Entreprise Server dans la forêt de ressources. En règle générale, les utilisateurs peuvent accéder Skype Entreprise fonctionnalités d’une autre forêt si les conditions suivantes sont remplies :
  - Les utilisateurs sont correctement synchronisés dans la forêt qui héberge Skype Entreprise. Dans les configurations hybrides, cela signifie que les utilisateurs doivent être synchronisés en tant qu’objets utilisateur désactivés.
  - La forêt qui héberge Skype Entreprise doit faire confiance à la forêt contenant les utilisateurs.
    Pour plus d’informations sur les scénarios hybrides de forêt de ressources, voir [Deploy a resource forest topology for hybrid Skype Entreprise](configure-a-multi-forest-environment-for-hybrid.md).

- **Déploiements multiples de Skype Entreprise Server dans plusieurs forêts.** Cette configuration peut survenir suite à des scénarios de fusion et d’acquisition, ainsi que dans des entreprises plus complexes. La consolidation de tous les utilisateurs locaux vers le cloud dans une seule organisation Microsoft 365 peut être réalisée pour n’importe quelle organisation avec plusieurs déploiements Skype Entreprise, à condition que les conditions clés suivantes soient remplies :
  - Il doit y avoir au plus un Microsoft 365'organisation impliquée. La consolidation dans les scénarios avec plusieurs organisations n’est pas prise en charge.
  - À tout moment, une seule forêt Skype Entreprise local peut être en mode hybride (espace d’adressace SIP partagé). Toutes les autres forêts Skype Entreprise sur site doivent rester entièrement sur site (et probablement fédérées les unes avec les autres). Notez que ces autres organisations locales peuvent se synchroniser avec AAD si vous le souhaitez avec de nouvelles fonctionnalités pour désactiver les domaines [SIP](/powershell/module/skype/disable-csonlinesipdomain) en ligne disponibles à partir de décembre 2018.

    Les clients avec des déploiements de Skype Entreprise dans plusieurs forêts doivent migrer entièrement chaque forêt Skype Entreprise individuellement vers l’organisation Microsoft 365 à l’aide de la fonctionnalité d’espace d’adressas SIP partagé. Une fois la migration de la forêt terminée, les clients doivent désactiver le déploiement hybride avec le déploiement local avant de migrer le déploiement local Skype Entreprise suivant. En outre, avant d’être migrés vers le cloud, les utilisateurs locaux restent dans un état fédéré avec tous les utilisateurs qui ne sont pas représentés dans l’annuaire local du même utilisateur. Pour plus d’informations, voir [Consolidation cloud pour Teams et Skype Entreprise](cloud-consolidation.md).

## <a name="federation-requirements"></a>Conditions requises pour la fédération

<a name="BKMK_Federation"> </a>

Lorsque vous configurez Skype Entreprise mode hybride, vous devez vous assurer que vos environnements locaux et en ligne peuvent se fédérer les uns avec les autres.  L’environnement en ligne dispose d’une fédération ouverte par défaut . L’environnement local a souvent fermé la fédération par défaut.  

Les conditions suivantes doivent être remplies pour configurer correctement un déploiement hybride :

- La correspondance de domaine doit être configurée de la même manière pour votre déploiement local et Microsoft 365 organisation. Si la découverte des partenaires est activée sur le déploiement local, la fédération ouverte doit être configurée pour votre organisation en ligne. Si la découverte des partenaires n’est pas activée, la fédération fermée doit être configurée pour votre organisation en ligne.
- La liste des domaines bloqués dans le déploiement local doit correspondre exactement à la liste des domaines bloqués de votre client en ligne.
- La liste des domaines autorisés dans le déploiement local doit correspondre exactement à la liste des domaines autorisés pour votre client en ligne.
- La fédération doit être activée pour les communications externes pour le client en ligne.

## <a name="network-considerations"></a>Considérations relatives au réseau

Les sections suivantes décrivent les éléments à prendre en compte pour :

- Paramètres DNS
- Considérations sur le pare-feu

### <a name="dns-settings-for-hybrid-deployments"></a>Paramètres DNS pour les déploiements hybrides

<a name="BKMK_DNS"> </a>

Lors de la création d’enregistrements DNS pour des déploiements hybrides, tous Skype Entreprise enregistrements DNS externes doivent pointer vers l’infrastructure locale. Pour plus d’informations sur les enregistrements DNS requis, reportez-vous aux exigences [DNS pour Skype Entreprise Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

En outre, vous devez vous assurer que la résolution DNS décrite dans le tableau suivant fonctionne dans votre déploiement local. (Si vous avez déjà configuré la fédération pour l’local, vous en avez probablement déjà.)

|Enregistrement DNS  <br/> |Résolvable par  <br/> |Enregistrement DNS requis  <br/> |
|:-----|:-----|:-----|
|Enregistrement DNS SRV pour _sipfederationtls._tcp.\<sipdomain.com\> pour tous les domaines SIP pris en charge résolvant les adresses IP externes du edge d’accès  <br/> |Serveurs Edge  <br/> |Activer la communication fédérée dans une configuration hybride. Le serveur Edge doit savoir où router le trafic fédéré pour le domaine SIP qui est réparti entre le trafic local et en ligne.  <br/> Doit utiliser une correspondance stricte de nom DNS entre le domaine dans le nom d’utilisateur et l’enregistrement SRV.  <br/> |
|DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)  <br/> |Ordinateurs des utilisateurs connectés au réseau d’entreprise interne  <br/> |Permettre aux utilisateurs en ligne de présenter ou d’afficher du contenu dans des réunions hébergées sur site. Le contenu inclut PowerPoint fichiers, tableaux blancs, sondages et notes partagées.  <br/> |

Selon la configuration du DNS dans votre organisation, vous devrez peut-être ajouter ces enregistrements à la zone DNS hébergée interne pour le ou les domaines SIP correspondants afin de fournir une résolution DNS interne à ces enregistrements.

### <a name="firewall-considerations-for-hybrid-deployments"></a>Considérations sur le pare-feu pour les déploiements hybrides

<a name="BKMK_Firewall"> </a>

Les ordinateurs de votre réseau doivent pouvoir effectuer des recherche DNS Internet standard. Si ces ordinateurs peuvent accéder à des sites Internet standard, votre réseau répond à cette exigence.

Selon l’emplacement de votre centre de données Microsoft Online Services, vous devez également configurer vos périphériques de pare-feu réseau pour accepter les connexions basées sur des noms de domaine génériques (par exemple, tout le trafic en provenance de \* .outlook.com). Si les pare-feu de votre organisation ne permettent pas la configuration des noms génériques, vous devez déterminer manuellement les plages d’adresses IP que vous souhaitez autoriser et les ports spécifiés.

Pour plus d’informations, notamment sur les ports et les protocoles requis, [voir Microsoft 365 URL et plages d’adresses IP.](/microsoft-365/enterprise/urls-and-ip-address-ranges)
