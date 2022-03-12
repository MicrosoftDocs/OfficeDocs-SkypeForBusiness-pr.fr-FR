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
search.appverid: MET150
description: Prévoyez d’implémenter la connectivité hybride entre Skype Entreprise Server et Teams en configurant Skype Entreprise mode hybride.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 242e365e190dcd915f7cc9f8e0989b7fc54a9206
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442470"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Planifier la connectivité hybride entre Skype Entreprise Server et Teams

> [!Important]
> Bien que Skype Entreprise Online ait été retiré depuis 2021, les produits locaux Skype Entreprise Server 2019, Skype Entreprise Server 2015 et Lync Server 2013 sont toujours pris en charge. En outre, Microsoft prend en charge les environnements hybrides entre ces produits locaux et les Microsoft Teams. Cela permet aux organisations avec ces déploiements locaux de migrer leurs utilisateurs vers TeamsOnly.  Enfin, l’édition Cloud Connector Skype Entreprise Server n’est plus prise en charge. Les clients qui ont besoin d’une connectivité PSTN sur site doivent utiliser [le routage direct](/MicrosoftTeams/direct-routing-landing-page).


Lisez cette rubrique pour découvrir comment planifier la connectivité hybride entre Skype Entreprise Server ou Lync Server 2013 et Teams. La configuration de la connectivité hybride est la première étape du déplacement de votre environnement local vers Microsoft Teams.

Si certains utilisateurs Skype Entreprise locaux utilisent déjà Teams (côte à côte), ils n’ont pas la possibilité d’interopérer avec les utilisateurs Skype Entreprise à partir de leur client Teams, ni de communiquer avec les utilisateurs d’organisations fédérées à partir de leur client Teams. Pour obtenir cette fonctionnalité dans Teams, ces utilisateurs doivent être déplacés de Skype Entreprise local vers le cloud afin qu’ils deviennent des utilisateurs TeamsOnly, ce qui nécessite la configuration Skype Entreprise mode hybride. Contrairement à l’utilisation côte à côte de Teams, lorsqu’un utilisateur est en mode TeamsOnly, tous les appels entrants et conversations de n’importe quel utilisateur arrivent dans le client Teams de l’utilisateur.

Vous devez également configurer la connectivité hybride et déplacer tous les utilisateurs vers le cloud avant de supprimer votre déploiement Skype Entreprise local.  Une fois la connectivité hybride configurée, vous pouvez choisir de migrer vos utilisateurs vers le cloud en fonction de votre planification et de vos besoins professionnels. Le routage direct vous permet de tirer parti de votre infrastructure vocale locale pendant votre migration vers le cloud et une fois celle-ci terminée.

Cette rubrique décrit l’infrastructure et la configuration système requises pour configurer la connectivité hybride entre votre déploiement local Skype Entreprise Server et votre Teams.

Une fois que vous avez lu cette rubrique et que vous êtes prêt à configurer la connectivité hybride, voir Configurer la connectivité hybride entre Skype Entreprise Server [et Teams](configure-hybrid-connectivity.md). Les rubriques de configuration fournissent des instructions pas à pas pour la configuration de la connectivité hybride entre votre déploiement local et Teams.


## <a name="implications-of-the-retirement-of-skype-for-business-online"></a>Implications du retrait de Skype Entreprise Online
Il est important de se souvenir qu’avant et après le retrait de Skype Entreprise Online, les utilisateurs Skype Entreprise Server sur site pouvaient utiliser Teams, mais ils ne pouvaient pas être TeamsOnly. (Les utilisateurs locaux sont en mode Îles par défaut). Les utilisateurs peuvent uniquement profiter des avantages complets de Teams, en particulier la fédération, la prise en charge PSTN et l’assurance que toutes les conversations et appels entrants sont arrivés en Teams, une fois qu’ils sont en mode TeamsOnly. 

Le retrait de Skype Entreprise Online n’a aucun impact sur le cycle de vie de support existant de Skype Entreprise Server ou Lync Server 2013.  Toutefois, le retrait de Skype Entreprise Online a eu un impact sur certains aspects de la transition des clients avec Skype Entreprise Server local ou Lync Server 2013, y compris les organisations hybrides existantes, vers le cloud. L’utilisation de l’environnement hybride comme moyen de passer de l’environnement local au cloud (par exemple, TeamsOnly) n’est pas impactée par le retrait de Skype Entreprise Online.

Avant le retrait de Skype Entreprise Online, les organisations hybrides pouvaient se composer de trois types d’utilisateurs de base : 
- Utilisateurs locaux (qui peuvent ou ne peuvent pas utiliser Teams, mais pas en mode Teams uniquement) 
- Utilisateurs en ligne avec tout mode de coexistence autre que TeamsOnly
- Utilisateurs TeamsOnly.

Après le retrait de Skype Entreprise Online, toutefois, les organisations hybrides ne peuvent être constituées que de deux types d’utilisateurs de base : 
- Les utilisateurs locaux (Qui peuvent ou non utiliser Teams, mais pas en mode TeamsOnly)
- Teams utilisateurs uniquement. 

Pour que les organisations passeront de Skype Entreprise Server ou Lync Server 2013 à Teams, elles doivent toujours configurer l’hybride à l’aide du même ensemble d’outils *, exactement* comme avant le retrait. Lors du déplacement d’un utilisateur de l’local vers TeamsOnly, il n’est plus nécessaire de spécifier le `-MoveToTeams` commutateur dans `Move-CsUser`. Auparavant, si ce commutateur n’était pas spécifié, les utilisateurs passaient du mode d’accueil Skype Entreprise Server local à Skype Entreprise Online, et leur mode était inchangé. Toutefois, étant donné que Skype Business Online a été retiré, le déplacement d’un utilisateur de l’local vers le cloud `Move-CsUser` avec affectera automatiquement le mode TeamsOnly et lancera la conversion de leurs réunions de l’local vers les réunions Teams,  `-MoveToTeams` que le commutateur soit spécifié ou non. Cela signifie également que les organisations avec Lync Server 2013, `MoveToTeams` qui n’ont jamais eu le commutateur, peuvent déplacer les utilisateurs directement vers TeamsOnly à partir de l’organisation locale. 

De même, si un nouvel utilisateur est créé directement dans Microsoft 365 plutôt que sur site, il aura automatiquement le mode Teams Uniquement quel que soit le mode du client. N’oubliez pas que dans une organisation hybride, les nouveaux utilisateurs doivent être créés dans Active Directory local (puis synchronisés dans Microsoft 365), plutôt que de créer directement un utilisateur dans Microsoft 365, afin de s’assurer que les utilisateurs locaux peuvent router vers le nouvel utilisateur.

Les modes de coexistence continuent d’exister après le retrait de Skype Entreprise Online. Comme auparavant, les utilisateurs  ayant des comptes Skype Entreprise Server sur site peuvent se voir attribuer n’importe quel mode de coexistence à l’exception de TeamsOnly. Toutefois, après la mise en retrait, les utilisateurs d’accueil en ligne ne peuvent être que TeamsOnly (contrairement au moment où les utilisateurs Skype Entreprise Online peuvent être n’importe quel mode). Il n’est plus possible d’affecter un mode autre que TeamsOnly à un utilisateur qui est en ligne.


> [!Important]
> Les organisations hybrides existantes avec des utilisateurs Skype Entreprise Online qui ne sont PAS TeamsOnly doivent se concentrer sur la mise à niveau de ces utilisateurs vers le mode Teams uniquement dès que possible. Si les utilisateurs de votre organisation sont toujours Skype Entreprise *Online* qui ne sont pas TeamsOnly, vous pouvez être programmé pour une mise à niveau assistée par Microsoft pour la transition de ces utilisateurs vers TeamsOnly. **Les mises à niveau Microsoft Assisted n’auront pas d’impact sur les utilisateurs qui sont Skype Entreprise Server sur site.** Les notifications de planification seront envoyées à l’avance aux clients hybrides dont les utilisateurs sont Skype Entreprise Online avant que ces utilisateurs en ligne ne soient mis à niveau vers Teams.

## <a name="about-shared-sip-address-space-functionality"></a>À propos de la fonctionnalité d’espace d’adressas SIP partagé

<a name="BKMK_Overview"> </a>

Avec la connectivité hybride définie entre un déploiement local de Skype Entreprise Server et Teams, vous pouvez avoir certains utilisateurs sur site et d’autres en ligne.

Ce type de configuration s’appuie sur la fonctionnalité d’espace d’adressamage SIP partagé et est parfois appelé « domaine fractioné », c’est-à-dire que les utilisateurs d’un domaine, tels que contoso.com, sont répartis entre l’utilisation de Skype Entreprise Server sur site et de Teams, comme illustré dans le diagramme suivant :

![Skype Entreprise hybride connectivité : domaine fractioné.](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Lorsque l’espace d’adressas SIP partagé est configuré :

- Azure Active Directory Connecter permet de synchroniser votre annuaire local avec les Microsoft 365.
- Les utilisateurs qui sont locaux interagissent avec les serveurs locaux Skype Entreprise serveurs.
- Les utilisateurs qui sont en ligne interagissent avec Teams.
- Les utilisateurs des deux environnements peuvent communiquer les uns avec les autres.
- Active Directory local fait autorité. Tous les utilisateurs doivent d’abord être créés dans l’annuaire Active Directory local, puis synchronisés avec Azure AD. Même si vous souhaitez que l’utilisateur soit homed online, vous devez d’abord créer l’utilisateur dans l’environnement local, puis le déplacer en ligne pour vous assurer que l’utilisateur est découvrable par les utilisateurs locaux.

Pour qu’un utilisateur puisse être déplacé en ligne, il doit se voir attribuer une licence Teams, ainsi que Skype Entreprise Online (Plan 2). **L’attribution de la licence Skype Entreprise Online est requise même après le retrait de Skype Entreprise Online.** Si vos utilisateurs souhaitent tirer parti de fonctionnalités en ligne supplémentaires, telles que l’audioconférence ou les Système téléphonique, vous devez leur attribuer la licence appropriée dans Microsoft 365.

## <a name="hybrid-connectivity-infrastructure-requirements"></a>Exigences relatives à l’infrastructure de connectivité hybride

<a name="BKMK_Infrastructure"> </a>

Pour implémenter la connectivité hybride entre votre environnement local et les services de communication Microsoft 365, vous devez respecter les exigences d’infrastructure suivantes :

- Déploiement local unique d’Skype Entreprise Server ou de Lync Server déployé dans une topologie prise en charge. Voir [la topologie requise](plan-hybrid-connectivity.md#BKMK_Topology) dans cette rubrique.

- Une Microsoft 365 organisation avec Teams.
    > [!NOTE]
    > Vous ne pouvez utiliser qu’un seul client pour une configuration hybride avec votre déploiement local.
    
- Azure Active Directory Connecter synchroniser votre annuaire local avec les Microsoft 365. Pour plus d’informations, [voir Azure AD Connecter : Comptes et autorisations](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

- Skype Entreprise Server d’administration. Ceux-ci sont nécessaires pour déplacer des utilisateurs de l’local vers le cloud. Ces outils doivent être installés sur un serveur ayant accès à la fois au déploiement local et à Internet.
- Outils d’administration en ligne. Vous pouvez utiliser le Centre d’administration Teams ou Windows PowerShell pour gérer les Teams. Pour utiliser PowerShell afin de gérer Teams, téléchargez et installez Teams module PowerShell. (Le Skype Entreprise Online Connector a été retiré).
- L’espace d’adressan SIP partagé doit être activé et votre déploiement local doit être configuré pour utiliser Microsoft 365 en tant que fournisseur d’hébergement. Pour plus d’informations sur les étapes requises pour configurer la connectivité hybride, voir [Configurer la connectivité hybride](configure-hybrid-connectivity.md).

Après avoir configuré la connectivité hybride, vous pouvez déplacer les utilisateurs vers Teams. Pour plus d’informations, voir [Move users from on-premises to Teams](move-users-from-on-premises-to-teams.md).

## <a name="server-version-requirements"></a>Conditions requises pour la version du serveur

<a name="BKMK_Topology"> </a>

Pour configurer votre déploiement hybride avec **Teams**, vous devez avoir l’une des topologies suivantes :

- Déploiement de Skype Entreprise Server 2019 avec tous les serveurs exécutant Skype Entreprise Server 2019.
- Déploiement de Skype Entreprise Server 2015 avec tous les serveurs exécutant Skype Entreprise Server 2015.
- Un déploiement Lync Server 2013 avec tous les serveurs exécutant Lync Server 2013.  Toutefois, si la connectivité vocale hybride est requise, vous devez utiliser une topologie de version mixte comme indiqué ci-dessous.
- Un déploiement avec un maximum de 2 versions de serveur différentes, comme répertorié ci-dessous :
  - Skype Entreprise Server 2015 et Skype Entreprise Server 2019
  - Lync Server 2013 et Skype Entreprise Server 2019
  - Lync Server 2013 et Skype Entreprise Server 2015

Si la voix hybride est souhaitée dans une topologie *, le* serveur Edge désigné comme serveur Edge de fédération ainsi que le pool associé à la fédération SIP doivent être en cours d’exécution Skype Entreprise 2015 ou version ultérieure. Les utilisateurs peuvent rester sur un pool Lync 2013 s’il en existe un. Pour plus d’informations, voir [Planifier votre solution vocale](/MicrosoftTeams/cloud-voice-landing-page).

> [!NOTE]
> - Le déplacement d’utilisateurs entre votre déploiement local et Teams nécessite désormais le protocole d’authentification OAuth. Auparavant, OAuth était recommandé, mais pas obligatoire. Skype Entreprise Server 2019 et Skype Entreprise Server 2015 CU12 (KB 3061064) nécessitent déjà OAuth. Si vous utilisez Skype Entreprise Server 2015 avec cu8 jusqu’à CU11, vous devez transmettre le commutateur -UseOAuth, qui garantit que le code local s’authentifiera à l’aide d’OAuth, ou de préférence la mise à niveau vers CU12. Si vous utilisez une version de Skype Entreprise Server 2015 antérieure à cu8, vous devez mettre à niveau vers CU12 ou version ultérieure. Si vous utilisez Lync Server 2013, vous devez d’abord mettre à niveau vers la mise à jour cumulative 10 de Lync Server 2013 (KB 2809243) ou une version ultérieure.
> - Lync Server 2010 n’est pas pris en charge avec Teams.


## <a name="multi-forest-support"></a>Prise en charge des environnements multi-forêts

<a name="BKMK_MultiForest"> </a>

Microsoft prend en charge les types de scénarios hybrides à forêts multiples suivants :

- **Topologie de forêt ressource.** Dans ce type de topologie, il existe une forêt qui héberge Skype Entreprise Server (la forêt de ressources), et il existe une ou plusieurs forêts supplémentaires qui hébergent des identités de compte, qui accèdent au Skype Entreprise Server dans la forêt de ressources. En règle générale, les utilisateurs peuvent accéder Skype Entreprise fonctionnalités d’une autre forêt si les conditions suivantes sont remplies :
  - Les utilisateurs sont correctement synchronisés dans la forêt qui héberge Skype Entreprise. Dans les configurations hybrides, cela signifie que les utilisateurs doivent être synchronisés en tant qu’objets utilisateur désactivés.
  - La forêt qui héberge Skype Entreprise doit faire confiance à la forêt contenant les utilisateurs.
    Pour plus d’informations sur les scénarios hybrides de forêt de ressources, voir [Deploy a resource forest topology for hybrid Skype Entreprise](configure-a-multi-forest-environment-for-hybrid.md).

- **Déploiements multiples de Skype Entreprise Server dans plusieurs forêts.** Cette configuration peut survenir suite à des scénarios de fusion et d’acquisition, ainsi que dans des entreprises plus complexes. La consolidation de tous les utilisateurs locaux vers le cloud dans une seule organisation Microsoft 365 peut être réalisée pour n’importe quelle organisation avec plusieurs déploiements Skype Entreprise, à condition que les conditions clés suivantes soient remplies :
  - Il doit y avoir au plus une organisation Microsoft 365 impliquée. La consolidation dans les scénarios avec plusieurs organisations n’est pas prise en charge.
  - À tout moment, une seule forêt Skype Entreprise local peut être en mode hybride (espace d’adressace SIP partagé). Toutes les autres forêts Skype Entreprise sur site doivent rester entièrement sur site (et probablement fédérées les unes avec les autres). Notez que ces autres organisations locales peuvent se synchroniser avec AAD si vous le souhaitez avec de nouvelles fonctionnalités pour désactiver les domaines [SIP](/powershell/module/skype/disable-csonlinesipdomain) en ligne disponibles à partir de décembre 2018.

    Les clients avec des déploiements de Skype Entreprise dans plusieurs forêts doivent migrer entièrement chaque forêt Skype Entreprise individuellement vers l’organisation Microsoft 365 à l’aide de la fonctionnalité d’espace d’adressas SIP partagé. Une fois la migration de la forêt terminée, les clients doivent désactiver le déploiement hybride avec le déploiement local avant de migrer le déploiement local Skype Entreprise suivant. En outre, avant d’être migrés vers le cloud, les utilisateurs locaux restent dans un état fédéré avec tous les utilisateurs qui ne sont pas représentés dans l’annuaire local du même utilisateur. Pour plus d’informations, voir [Consolidation cloud pour Teams et Skype Entreprise](cloud-consolidation.md).

## <a name="federation-requirements"></a>Conditions requises pour la fédération

<a name="BKMK_Federation"> </a>

Lorsque vous configurez Skype Entreprise mode hybride, vous devez vous assurer que vos environnements locaux et en ligne peuvent se fédérer les uns avec les autres.  L’environnement en ligne dispose d’une fédération ouverte par défaut . L’environnement local a souvent fermé la fédération par défaut.  

Les conditions suivantes doivent être remplies pour configurer correctement un déploiement hybride :

- La correspondance de domaine doit être configurée de la même manière pour votre déploiement local et votre Microsoft 365 organisation. Si la découverte des partenaires est activée sur le déploiement local, la fédération ouverte doit être configurée pour votre organisation en ligne. Si la découverte des partenaires n’est pas activée, la fédération fermée doit être configurée pour votre organisation en ligne.
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
|Enregistrement DNS SRV pour _sipfederationtls._tcp.\<sipdomain.com\> pour tous les domaines SIP pris en charge résolvant les adresses IP externes du edge d’accès  <br/> |Serveurs Edge  <br/> |Activer la communication fédérée dans une configuration hybride. Le serveur Edge doit savoir où router le trafic fédéré pour le domaine SIP qui est réparti entre le site local et en ligne.  <br/> Doit utiliser une correspondance de nom DNS stricte entre le domaine dans le nom d’utilisateur et l’enregistrement SRV.  <br/> |
|DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)  <br/> |Ordinateurs des utilisateurs connectés au réseau d’entreprise interne  <br/> |Permettre aux utilisateurs en ligne de présenter ou d’afficher du contenu dans des réunions hébergées sur site. Le contenu inclut PowerPoint fichiers, tableaux blancs, sondages et notes partagées.  <br/> |

Selon la configuration du DNS dans votre organisation, vous devrez peut-être ajouter ces enregistrements à la zone DNS hébergée interne pour le ou les domaines SIP correspondants afin de fournir une résolution DNS interne à ces enregistrements.

### <a name="firewall-considerations-for-hybrid-deployments"></a>Considérations sur le pare-feu pour les déploiements hybrides

<a name="BKMK_Firewall"> </a>

Les ordinateurs de votre réseau doivent pouvoir effectuer des recherche DNS Internet standard. Si ces ordinateurs peuvent accéder à des sites Internet standard, votre réseau répond à cette exigence.

Selon l’emplacement de votre centre de données Microsoft Online Services, vous devez également configurer vos périphériques de pare-feu réseau pour accepter les connexions basées sur des noms de domaine génériques (par exemple, \*tout le trafic en provenance de .outlook.com). Si les pare-feu de votre organisation ne permettent pas la configuration des noms génériques, vous devez déterminer manuellement les plages d’adresses IP que vous souhaitez autoriser et les ports spécifiés.

Pour plus d’informations, notamment sur les ports et les protocoles requis, voir [Microsoft 365 URL et plages d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges).
