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
description: Prévoyez d’implémenter une connectivité hybride entre Skype Entreprise Server et Teams en configurant Skype Entreprise mode hybride.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: a73b14a3642a216ff9cbbe919b586979aabf6a81
ms.sourcegitcommit: 15ec17eff4ad4c962d00b8683513f9b269d82917
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2022
ms.locfileid: "66695047"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Planifier la connectivité hybride entre Skype Entreprise Server et Teams

> [!Important]
> Bien que Skype Entreprise Online ait été retiré depuis 2021, les produits locaux Skype Entreprise Server 2019, Skype Entreprise Server 2015 et Lync Server 2013 sont toujours pris en charge. En outre, Microsoft prend en charge les environnements hybrides entre ces produits locaux et Microsoft Teams. Cela permet aux organisations disposant de ces déploiements locaux de migrer leurs utilisateurs vers TeamsOnly.  Enfin, l’édition Cloud Connector de Skype Entreprise Server n’est plus prise en charge. Les clients nécessitant une connectivité RTC locale doivent utiliser le [routage direct](/MicrosoftTeams/direct-routing-landing-page).


Lisez cette rubrique pour savoir comment planifier la connectivité hybride entre Skype Entreprise Server ou Lync Server 2013 et Teams. La configuration de la connectivité hybride est la première étape du déplacement de votre environnement local vers un environnement Microsoft Teams uniquement dans le cloud.

Dans un déploiement local de Skype Entreprise Server, les utilisateurs de Skype Entreprise peuvent également utiliser Teams, mais toutes les fonctionnalités Teams ne sont pas disponibles pour ces utilisateurs tant qu’ils sont configurés pour utiliser le déploiement Skype Entreprise Server local. Ces utilisateurs sont dits « hébergés » localement, et certaines fonctionnalités teams ne sont pas disponibles alors que ces utilisateurs sont hébergés localement, par exemple :

- Les appels fédérés et les conversations via le client Teams de l’utilisateur avec des utilisateurs d’autres organisations ne sont pas disponibles
- Interop communication via le client Teams de l’utilisateur avec d’autres utilisateurs de l’organisation qui utilisent Skype Entreprise client.
- Fonctionnalité d’appel RTC (si une licence système téléphonique est attribuée à l’utilisateur).

Pour bénéficier d’une fonctionnalité Teams complète, ces utilisateurs doivent être déplacés de Skype Entreprise localement vers le cloud, auquel cas l’utilisateur devient TeamsOnly. Le déplacement d’un utilisateur d’un environnement local vers le cloud définit le mode de coexistence de l’utilisateur sur TeamsOnly. Une fois que les utilisateurs sont déplacés vers le cloud et TeamsOnly, toutes les conversations et appels entrants arrivent dans leur client Teams (contrairement à l’utilisation côte à côte de Teams).  Pour plus d’informations, consultez [la coexistence de Teams avec Skype Entreprise et des conseils sur la migration](/microsoftteams/coexistence-chat-calls-presence) et [l’interopérabilité pour les organisations utilisant Teams avec Skype Entreprise](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

Le déplacement d’utilisateurs entre l’environnement local et TeamsOnly dans le cloud nécessite la configuration de Skype Entreprise mode hybride. En outre, avant de désactiver votre déploiement Skype Entreprise local, déplacez tous les utilisateurs de l’environnement local vers le cloud.   Une fois la connectivité hybride configurée, vous pouvez choisir de migrer vos utilisateurs vers le cloud en fonction de votre planification et de vos besoins professionnels.  Le routage direct vous permet de tirer parti de votre infrastructure vocale locale pendant votre migration vers le cloud et une fois celle-ci terminée.

Cette rubrique décrit la configuration requise pour l’infrastructure et le système dont vous aurez besoin pour configurer la connectivité hybride entre votre déploiement local Skype Entreprise Server existant et Teams.

Une fois que vous avez lu cette rubrique et que vous êtes prêt à configurer la connectivité hybride, consultez [Configurer la connectivité hybride entre Skype Entreprise Server et Teams](configure-hybrid-connectivity.md). Les rubriques de configuration fournissent des instructions pas à pas pour la configuration de la connectivité hybride entre votre déploiement local et Teams.


## <a name="implications-of-the-retirement-of-skype-for-business-online"></a>Implications du retrait de Skype Entreprise Online
Il est important de se rappeler qu’avant et après la mise hors service de Skype Entreprise Online, les utilisateurs hébergés dans Skype Entreprise Server local peuvent utiliser Teams, mais ils ne peuvent pas être TeamsOnly. (Les utilisateurs locaux sont en mode Îles par défaut et se voient attribuer n’importe quel mode autre que TeamsOnly). Les utilisateurs peuvent uniquement bénéficier des avantages complets de Teams, en particulier la fédération, la prise en charge rtc et l’assurance que toutes les conversations et appels entrants arrivent dans Teams, une fois qu’ils sont en mode TeamsOnly. 

Le retrait de Skype Entreprise Online n’a aucun impact sur le cycle de vie de support existant de Skype Entreprise Server ou Lync Server 2013.  Toutefois, le retrait de Skype Entreprise Online a eu un impact sur certains aspects de la **façon dont** *les utilisateurs passent au cloud et deviennent TeamsOnly* dans les organisations avec des Skype Entreprise Server locaux ou Lync Server 2013, y compris les organisations hybrides existantes. L’utilisation de l’hybride comme configuration prérequise pour passer d’un environnement local au cloud (par exemple, TeamsOnly) reste inchangée.

Avant la mise hors service de Skype Entreprise Online, les organisations hybrides pouvaient se composer de trois types d’utilisateurs de base : 
- Utilisateurs locaux (qui peuvent ou non utiliser Teams, mais pas en mode Teams uniquement) 
- Utilisateurs en ligne avec n’importe quel mode de coexistence autre que TeamsOnly
- Utilisateurs TeamsOnly.

Toutefois, après la mise hors service de Skype Entreprise Online, les organisations hybrides ne peuvent se composer que de deux types d’utilisateurs de base : 
- Utilisateurs locaux (qui peuvent ou non utiliser Teams, mais pas en mode TeamsOnly)
- Teams uniquement les utilisateurs. 

Pour que les organisations passent de Skype Entreprise Server ou Lync Server 2013 à Teams, elles doivent toujours configurer et configurer l’hybride à l’aide du même ensemble d’outils, *exactement comme avant la mise hors service*. Lors du déplacement d’un utilisateur d’un site local vers TeamsOnly, il n’est plus nécessaire de spécifier le `-MoveToTeams` commutateur dans `Move-CsUser`. Auparavant, si ce commutateur n’était pas spécifié, les utilisateurs sont passés de Skype Entreprise Server local à Skype Entreprise Online, et leur mode est resté inchangé. Toutefois, étant donné que Skype Business Online a été mis hors service, le déplacement d’un utilisateur d’un site local vers le cloud avec `Move-CsUser` affecter *automatiquement* le mode TeamsOnly et lancer la conversion de ses réunions d’un site local vers des réunions Teams, que le `-MoveToTeams` commutateur soit spécifié ou non. Cela signifie également que les organisations avec Lync Server 2013, qui n’a jamais eu le `MoveToTeams` commutateur, peuvent déplacer les utilisateurs directement vers TeamsOnly à partir d’un emplacement local. 

De même, si un nouvel utilisateur est créé directement dans Microsoft 365 plutôt qu’en local, il dispose automatiquement du mode Teams Uniquement, quel que soit le mode du locataire. Gardez à l’esprit que dans une organisation hybride avec au moins un utilisateur local, les nouveaux utilisateurs doivent être créés dans le Active Directory local (puis synchronisés dans Microsoft 365), plutôt que de créer directement un utilisateur dans Microsoft 365, pour vous assurer que les utilisateurs locaux peuvent router vers le nouvel utilisateur *, même si vous envisagez que le nouvel utilisateur soit un utilisateur cloud*. Une fois créés dans le répertoire local, ces nouveaux utilisateurs doivent être *activés par sip dans le* déploiement Skype Entreprise local, puis, si vous le souhaitez, déplacés vers le cloud pour devenir TeamsOnly. 

Les modes de coexistence continuent d’exister après la mise hors service de Skype Entreprise Online. Comme précédemment, les utilisateurs disposant de comptes hébergés dans Skype Entreprise Server localement peuvent se faire attribuer n’importe quel mode de coexistence, à l’exception de TeamsOnly. Toutefois, après la mise hors service, les utilisateurs hébergés en ligne ne peuvent être que TeamsOnly. Il n’est plus possible d’affecter un mode autre que TeamsOnly à un utilisateur hébergé en ligne.


> [!Important]
> Les organisations hybrides existantes avec des utilisateurs hébergés dans Skype Entreprise Online qui ne sont pas TeamsOnly doivent se concentrer sur la mise à niveau de ces utilisateurs vers le mode Teams uniquement dès que possible. Si votre organisation a toujours des utilisateurs hébergés dans Skype Entreprise *Online* qui ne sont pas TeamsOnly, vous serez planifié pour une mise à niveau assistée par Microsoft pour faire passer ces utilisateurs à TeamsOnly. **Les mises à niveau assistées par Microsoft n’auront pas d’impact sur les utilisateurs hébergés dans Skype Entreprise Server localement.** Les notifications de planification seront envoyées à l’avance aux clients hybrides avec des utilisateurs hébergés dans Skype Entreprise Online avant que ces utilisateurs en ligne et non TeamsOnly soient mis à niveau vers Teams.

## <a name="about-shared-sip-address-space-functionality"></a>À propos de la fonctionnalité Espace d’adressage SIP partagé

<a name="BKMK_Overview"> </a>

Avec la connectivité hybride configurée entre un déploiement local de Skype Entreprise Server et Teams, certains utilisateurs peuvent être hébergés localement et certains utilisateurs hébergés en ligne.

Ce type de configuration s’appuie sur la fonctionnalité d’espace d’adressage SIP partagé et est parfois appelé « domaine fractionné », c’est-à-dire que les utilisateurs d’un domaine, tels que contoso.com, sont divisés entre l’utilisation de Skype Entreprise Server localement et Teams, comme illustré dans le diagramme suivant :

![connectivité Skype Entreprise hybride : domaine fractionné.](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Lorsque l’espace d’adressage SIP partagé est configuré :

- Azure Active Directory Connect est utilisé pour synchroniser votre annuaire local avec Microsoft 365.
- Les utilisateurs hébergés localement interagissent avec les serveurs Skype Entreprise locaux.
- Les utilisateurs hébergés en ligne interagissent avec Teams.
- Les utilisateurs des deux environnements peuvent communiquer entre elles.
- Le Active Directory local fait autorité. Tous les utilisateurs doivent d’abord être créés dans le Active Directory local, puis synchronisés avec Azure AD. Même si vous envisagez que l’utilisateur soit hébergé en ligne, vous devez d’abord créer l’utilisateur dans l’environnement local, puis déplacer l’utilisateur vers la ligne pour vous assurer que l’utilisateur est détectable par les utilisateurs locaux.

Pour qu’un utilisateur puisse être déplacé en ligne, une licence Teams doit lui être attribuée, ainsi que Skype Entreprise Online (Plan 2). **L’attribution de la licence Skype Entreprise Online est requise même après la mise hors service de Skype Entreprise Online.** Si vos utilisateurs souhaitent tirer parti d’autres fonctionnalités en ligne, telles que l’audioconférence ou le système téléphonique, vous devez leur attribuer la licence appropriée dans Microsoft 365.

## <a name="hybrid-connectivity-infrastructure-requirements"></a>Configuration requise pour l’infrastructure de connectivité hybride

<a name="BKMK_Infrastructure"> </a>

Pour implémenter une connectivité hybride entre votre environnement local et les services de communication Microsoft 365, vous devez répondre aux exigences d’infrastructure suivantes :

- Déploiement local unique d’Skype Entreprise Server ou de Lync Server déployé dans une topologie prise en charge. Consultez [les exigences en matière de topologie](plan-hybrid-connectivity.md#BKMK_Topology) dans cette rubrique.

- Organisation Microsoft 365 avec Teams.
    > [!NOTE]
    > Vous ne pouvez utiliser qu’un seul locataire pour une configuration hybride avec votre déploiement local.
    
- Azure Active Directory Connect pour synchroniser votre annuaire local avec Microsoft 365. Pour plus d’informations, consultez [Azure AD Connect : comptes et autorisations](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

- Skype Entreprise Server outils d’administration. Celles-ci sont nécessaires pour déplacer les utilisateurs d’un emplacement local vers le cloud. Ces outils doivent être installés sur un serveur ayant accès à la fois au déploiement sur site et à Internet.
- Outils d’administration en ligne. Vous pouvez utiliser le Centre d’administration Teams ou Windows PowerShell pour gérer Teams. Pour utiliser PowerShell pour gérer Teams, téléchargez et installez le module Teams PowerShell. (Le connecteur Skype Entreprise Online a été mis hors service).
- L’espace d’adressage SIP partagé doit être activé et votre déploiement local doit être configuré pour utiliser Microsoft 365 en tant que fournisseur d’hébergement. Pour plus d’informations sur les étapes nécessaires à la configuration de la connectivité hybride, consultez [Configurer la connectivité hybride](configure-hybrid-connectivity.md).

Après avoir configuré la connectivité hybride, vous pouvez déplacer des utilisateurs vers Teams. Pour plus d’informations, consultez [Déplacer des utilisateurs d’un site local vers Teams](move-users-from-on-premises-to-teams.md).

## <a name="server-version-requirements"></a>Configuration requise pour la version du serveur

<a name="BKMK_Topology"> </a>

Pour configurer votre déploiement hybride avec **Teams**, vous devez disposer de l’une des topologies prises en charge suivantes :

- Déploiement de Skype Entreprise Server 2019 avec tous les serveurs exécutant Skype Entreprise Server 2019.
- Déploiement de Skype Entreprise Server 2015 avec tous les serveurs exécutant Skype Entreprise Server 2015.
- Un déploiement Lync Server 2013 avec tous les serveurs exécutant Lync Server 2013.  Toutefois, si la connectivité vocale hybride est requise, vous devez utiliser une topologie de version mixte, comme indiqué ci-dessous.
- Déploiement avec un maximum de 2 versions de serveur différentes, comme indiqué ci-dessous :
  - Skype Entreprise Server 2015 et Skype Entreprise Server 2019
  - Lync Server 2013 et Skype Entreprise Server 2019
  - Lync Server 2013 et Skype Entreprise Server 2015
- À compter du 31 juillet 2022, pour déplacer des utilisateurs entre un déploiement local et le cloud, vous devez utiliser les versions minimales suivantes de Skype Entreprise Server ou de Lync Server :
</br>

|Produit local|Version minimale requise|Build minimale requise|
|---|---|---|
|Skype Entreprise Server 2019| CU6 |7.0.2046.385|
|Skype Entreprise Server 2015| CU12|6.0.9319.619|
|Lync Server 2013| CU10 avec correctif logiciel 7|5.0.8308.1182|

</br>

> [!NOTE] 
> Lync Server 2010 n’est pas pris en charge avec Teams.


## <a name="multi-forest-support"></a>Prise en charge des environnements multi-forêts

<a name="BKMK_MultiForest"> </a>

Microsoft prend en charge les types suivants de scénarios hybrides à forêts multiples :

- **Topologie de la forêt ressource.** Dans ce type de topologie, il existe une forêt qui héberge Skype Entreprise Server (la forêt de ressources), et il existe une ou plusieurs forêts supplémentaires qui hébergent des identités de compte, qui accèdent à la Skype Entreprise Server dans la forêt de ressources. En général, les utilisateurs peuvent accéder à la fonctionnalité Skype Entreprise dans une autre forêt si les conditions suivantes sont remplies :
  - Les utilisateurs sont correctement synchronisés dans la forêt qui héberge Skype Entreprise. Dans les configurations hybrides, cela signifie que les utilisateurs doivent être synchronisés en tant qu’objets utilisateur désactivés.
  - La forêt hébergeant Skype Entreprise doit approuver la forêt contenant les utilisateurs.
    Pour plus d’informations sur les scénarios hybrides de forêt de ressources, consultez [Déployer une topologie de forêt de ressources pour les Skype Entreprise hybrides](configure-a-multi-forest-environment-for-hybrid.md).

- **Plusieurs déploiements de Skype Entreprise Server dans plusieurs forêts.** Cette configuration peut découler de scénarios de fusion et d’acquisition, ainsi que dans des entreprises plus complexes. La consolidation de tous les utilisateurs locaux vers le cloud au sein d’une seule organisation Microsoft 365 peut être obtenue pour toute organisation avec plusieurs déploiements Skype Entreprise, à condition que les exigences clés suivantes soient remplies :
  - Il doit y avoir au plus une organisation Microsoft 365 impliquée. La consolidation dans les scénarios avec plusieurs organisations n’est pas prise en charge.
  - À tout moment, une seule forêt Skype Entreprise sur site peut être en mode hybride (espace d’adressage SIP partagé). Toutes les autres forêts Skype Entreprise locales doivent rester entièrement locales (et probablement fédérées les unes avec les autres). Notez que ces autres organisations locales peuvent se synchroniser avec AAD si vous le souhaitez avec de [nouvelles fonctionnalités pour désactiver les domaines SIP en ligne disponibles](/powershell/module/skype/disable-csonlinesipdomain) à compter de décembre 2018.

    Les clients avec des déploiements de Skype Entreprise dans plusieurs forêts doivent migrer entièrement chaque forêt Skype Entreprise individuellement vers l’organisation Microsoft 365 à l’aide de la fonctionnalité de domaine partagé (espace d’adressage SIP partagé). Une fois la migration de forêt terminée, les clients doivent désactiver l’hybride avec le déploiement local avant de migrer le déploiement Skype Entreprise local suivant. En outre, avant d’être migrés vers le cloud, les utilisateurs locaux restent dans un état fédéré avec tous les utilisateurs qui ne sont pas représentés dans le répertoire local du même utilisateur. Pour plus d’informations, consultez [consolidation du cloud pour Teams et Skype Entreprise](cloud-consolidation.md).

## <a name="federation-requirements"></a>Configuration requise pour la fédération

<a name="BKMK_Federation"> </a>

Lorsque vous configurez Skype Entreprise mode hybride, vous devez vous assurer que vos environnements locaux et en ligne peuvent se fédérer les uns avec les autres.  L’environnement en ligne dispose d’une fédération ouverte par défaut ; l’environnement local a souvent fermé la fédération par défaut.  

Les conditions suivantes doivent être remplies pour configurer correctement un déploiement hybride :

- La correspondance de domaine doit être configurée de la même manière pour votre déploiement local et votre organisation Microsoft 365. Si la découverte de partenaire est activée sur le déploiement local, la fédération ouverte doit être configurée pour votre organisation en ligne. Si la découverte de partenaire n’est pas activée, la fédération fermée doit être configurée pour votre organisation en ligne.
- La liste des domaines bloqués dans le déploiement local doit correspondre exactement à la liste des domaines bloqués pour votre locataire en ligne.
- La liste des domaines autorisés dans le déploiement local doit correspondre exactement à la liste des domaines autorisés pour votre locataire en ligne.
- La fédération doit être activée pour les communications externes pour le locataire en ligne.

## <a name="network-considerations"></a>Considérations relatives au réseau

Les sections suivantes décrivent les considérations suivantes pour :

- Paramètres DNS
- Considérations relatives au pare-feu

### <a name="dns-settings-for-hybrid-deployments"></a>Paramètres DNS pour les déploiements hybrides

<a name="BKMK_DNS"> </a>

Lors de la création d’enregistrements DNS pour les déploiements hybrides, tous les enregistrements DNS externes Skype Entreprise doivent pointer vers l’infrastructure locale. Pour plus d’informations sur les enregistrements DNS requis, reportez-vous aux [exigences DNS pour Skype Entreprise Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

En outre, vous devez vous assurer que la résolution DNS décrite dans le tableau suivant fonctionne dans votre déploiement local. (Si vous avez déjà configuré la fédération pour l’environnement local, vous en avez probablement déjà.)

|Enregistrement DNS  <br/> |Pouvant être résolu par  <br/> |Enregistrement DNS requis  <br/> |
|:-----|:-----|:-----|
|Enregistrement SRV DNS pour _sipfederationtls._tcp.\<sipdomain.com\> pour tous les domaines SIP pris en charge résolvant les adresses IP externes Access Edge  <br/> |Serveur(s) Edge  <br/> |Activez la communication fédérée dans une configuration hybride. Le serveur Edge doit savoir où router le trafic fédéré pour le domaine SIP qui est fractionné entre localement et en ligne.  <br/> Doit utiliser une correspondance de nom DNS stricte entre le domaine dans le nom d’utilisateur et l’enregistrement SRV.  <br/> |
|Enregistrements DNS A pour le nom de domaine complet du service de conférence web Edge, par exemple, webcon.contoso.com résolution des adresses IP externes Edge de conférence web  <br/> |Ordinateurs des utilisateurs connectés au réseau d’entreprise interne  <br/> |Permettre aux utilisateurs en ligne de présenter ou d’afficher du contenu dans des réunions hébergées localement. Le contenu inclut des fichiers PowerPoint, des tableaux blancs, des sondages et des notes partagées.  <br/> |

Selon la façon dont DNS est configuré dans votre organisation, vous devrez peut-être ajouter ces enregistrements à la zone DNS hébergée interne pour le ou les domaines SIP correspondants afin de fournir une résolution DNS interne à ces enregistrements.

### <a name="firewall-considerations-for-hybrid-deployments"></a>Considérations relatives au pare-feu pour les déploiements hybrides

<a name="BKMK_Firewall"> </a>

Les ordinateurs du réseau doivent être en mesure d’effectuer des recherches DNS Internet. Si ces ordinateurs peuvent accéder à des sites Internet standard, votre réseau répond à cette exigence.

Selon l’emplacement de votre centre de données Microsoft Online Services, vous devez également configurer vos appareils de pare-feu réseau pour accepter les connexions basées sur des noms de domaine génériques (par exemple, tout le trafic provenant de \*.outlook.com). Si les pare-feu de votre organisation ne prennent pas en charge les configurations de nom génériques, vous devrez déterminer manuellement les plages d’adresses IP que vous voulez autoriser et les ports.

Pour plus d’informations, notamment sur les ports et les exigences de protocole, consultez [les URL et plages d’adresses IP Microsoft 365](/microsoft-365/enterprise/urls-and-ip-address-ranges).
