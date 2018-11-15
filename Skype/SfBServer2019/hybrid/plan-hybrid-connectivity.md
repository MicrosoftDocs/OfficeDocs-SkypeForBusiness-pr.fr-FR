---
title: Planification de la connectivité hybride
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Considérations pour l’implémentation de connectivité hybride entre Skype pour Business Server et Skype pour Business Online ou équipes de planification.
ms.openlocfilehash: 2f702989a0d40e7bce9b0f3612d67fd374d0813c
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531652"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Planification de la connectivité hybride entre Skype pour Business Server et Office 365

## <a name="overview"></a>Vue d’ensemble

Lisez cette rubrique pour savoir comment planifier la connectivité hybride entre Skype pour Business Server et les équipes ou Skype pour Business Online. Configurer la connectivité hybride est la première étape de déplacement de votre environnement local vers le nuage.

Si vous avez Skype sur site pour les utilisateurs professionnels qui utilisent également des équipes (côte à côte), ces utilisateurs n’ont pas la possibilité d’interagir avec Skype pour les utilisateurs professionnels à partir du client de leurs équipes, ni communiquer avec les utilisateurs dans les organisations fédérées, à partir de leur Client d’équipes. Pour bénéficier de cette fonctionnalité dans les équipes, ces utilisateurs doivent être déplacés à partir de Skype pour Business local vers le nuage, qui requiert la configuration Skype pour le mode hybride Business. En outre, pour une meilleure pratique, ces utilisateurs doivent être en mode uniquement les équipes qui garantit tous les appels entrants et conversations à partir de n’importe quel terrestre utilisateur dans le client de l’utilisateur aux équipes.

Configurer la connectivité hybride et de déplacement de tous les utilisateurs vers le nuage sont également requis avant que vous désactiviez votre Skype sur site pour le déploiement d’entreprise.  Connectivité hybride configurer, vous pouvez choisir à déplacer les utilisateurs vers le nuage en fonction des besoins de votre calendrier et d’entreprise. Avec le routage Direct, vous pouvez exploiter votre infrastructure de voix sur site pendant que vous déplacez vers le nuage et après que la migration est terminée.

Cette rubrique décrit l’infrastructure et vous devez configurer la connectivité hybride entre votre configuration requise locaux Skype pour le déploiement de serveurs d’entreprise et des équipes ou Skype pour Business Online.

Une fois que vous avez lu cet article et que vous êtes prêt à configurer la connectivité hybride, consultez [configurer la connectivité hybride entre Skype pour Business Server et Office 365](configure-hybrid-connectivity.md). Les rubriques de configuration fournissent des instructions détaillées pour la configuration de la connectivité hybride entre votre déploiement sur site et les équipes ou Skype pour Business en ligne.


## <a name="about-split-domain-functionality"></a>Les fonctionnalités de domaine fractionné
<a name="BKMK_Overview"> </a>

 Connectivité hybride entre un déploiement local de Skype pour Business Server et les équipes ou Skype pour Business Online, vous pouvez avoir certains utilisateurs hébergés sur un système local et certains utilisateurs hébergement en ligne.

Ce type de configuration s’appuie sur les fonctionnalités de l’espace adresse SIP partagées et est parfois appelé « domaine fragmenté », ce qui signifie que les utilisateurs d’un domaine, par exemple, contoso.com, sont répartis entre l’utilisation de Skype pour Business Server sur site et des équipes ou Skype pour les entreprises En ligne, comme illustré dans le diagramme suivant : 

![Connectivité hybride SfB - domaine partagé](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Lorsque l’espace d’adressage SIP partagé est configuré :

- Azure Active Directory se connecter permet de synchroniser votre annuaire local avec Office 365.

- Les utilisateurs qui sont hébergés sur site interagissent avec Skype locaux des serveurs d’entreprise. 

- Les utilisateurs hébergés en ligne peuvent interagir avec Skype pour des services professionnels en ligne ou des équipes.

- Les utilisateurs à partir des deux environnements peuvent communiquer entre eux. 

- Active Directory local fait autorité. Tous les utilisateurs doivent être créés dans Active Directory local en premier et puis synchronisés avec Azure AD. Même si vous avez l’intention de l’utilisateur à être hébergé en ligne, vous devez d’abord créer l’utilisateur dans l’environnement local et puis déplacer l’utilisateur en ligne pour s’assurer de que l’utilisateur est détectable par les utilisateurs locaux. 

Avant d’un utilisateur peut être déplacé en ligne, l’utilisateur doit être affecté un Skype licence entreprise Online (Plan 2). Si l’utilisateur utilise des équipes, l’utilisateur doit également être affecté à une licence équipes (et la Skype licence entreprise doit demeurer activé). Si vous souhaitent que vos utilisateurs à tirer parti des fonctionnalités en ligne supplémentaires, telles que la conférence Audio ou système téléphonique, vous devez affecter la licence appropriée dans Office 365.


## <a name="infrastructure-requirements"></a>Conditions requises pour l'infrastructure
<a name="BKMK_Infrastructure"> </a>

Pour implémenter la connectivité hybride entre votre environnement local et les services de communication Office 365, vous devez remplir les conditions d’infrastructure suivantes :

- Un seul déploiement local de Skype pour Business Server ou un serveur Lync qui est déployé dans une topologie prise en charge. Dans cette rubrique, voir [Configuration requise de topologie](plan-hybrid-connectivity.md#BKMK_Topology) .

- Un client Microsoft Office 365 avec Skype pour Business Online activé.

    > [!NOTE]
    > Vous ne pouvez utiliser qu'un seul client pour une configuration hybride avec votre déploiement local.

- Azure Active Directory Connect pour synchroniser votre répertoire sur site avec Office 365. Pour plus d’informations, voir [Azure AD Connect : comptes et autorisations](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

- Skype pour les outils d’administration Business Server.  Elles sont requises pour déplacer les utilisateurs locaux vers le nuage. Ces outils doivent être installés sur un serveur ayant accès à un déploiement local et internet. 

- Outils d’administration en ligne.  Vous pouvez utiliser les équipes et le Skype pour le centre d’administration Business ou de Windows PowerShell pour gérer des équipes et Skype pour Business Online. Pour utiliser PowerShell pour gérer des équipes ou Skype pour Business Online, téléchargez et installez le Skype pour Business Connector en ligne. 

- Espace d’adressage SIP partagé doit être activé, et que votre déploiement sur site doit être configuré pour utiliser Office 365 comme fournisseur d’hébergement. Pour plus d’informations sur les étapes nécessaires pour configurer la connectivité hybride, voir [connectivité de configuration hybride](configure-hybrid-connectivity.md).

Après avoir configuré la connectivité hybride, vous pouvez déplacer des utilisateurs à des équipes ou Skype pour Business Online. Pour plus d’informations, voir [déplacer des utilisateurs sur site aux équipes](move-users-from-on-premises-to-teams.md) et [déplacer les utilisateurs à partir de sur site à Skype pour Business Online](move-users-from-on-premises-to-skype-for-business-online.md).


## <a name="topology-requirements"></a>Conditions requises pour la topologie
<a name="BKMK_Topology"> </a>

Pour configurer votre déploiement hybride avec **des équipes ou Skype pour Business Online**, vous devez disposer d’un des topologies prises en charge suivantes :

- Un Skype pour le déploiement d’entreprise Server 2019 avec tous les serveurs exécutant Skype pour Business Server 2019. 
- Un Skype pour le déploiement d’entreprise Server 2015 avec tous les serveurs exécutant Skype pour Business Server 2015.
- Un déploiement de Lync Server 2013 avec tous les serveurs exécutant Lync Server 2013.  Toutefois, si la connectivité de voix hybride est requise, vous devez utiliser une topologie mixte version, comme indiqué ci-dessous.
- Un déploiement avec un maximum de 2 différentes versions serveur comme indiqué ci-dessous :
  - Skype pour Business Server 2015 et Skype pour Business Server 2019
  - Lync Server 2013 et Skype pour Business Server 2019
  - Lync Server 2013 et Skype pour Business Server 2015

*Si vous souhaitez voix hybride dans n’importe quelle topologie*, le serveur de périphérie qui est désigné comme la fédération Edge, ainsi que le pool associé à la fédération SIP doit exécuter Skype pour Business 2015 ou version ultérieure. Les utilisateurs peuvent rester dans un Pool Lync 2013 si elle existe. Pour plus d’informations, voir [Planifier le système téléphonique avec une connectivité PSTN dans Skype pour Business Server](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).

Les topologies suivantes qui incluent **Lync Server 2010 sont pris en charge avec Skype pour Business en ligne** pour la messagerie instantanée et les réunions.  Topologies qui incluent des **Lync Server 2010 ne sont pas pris en charge pour la voix hybride ni les équipes**.

- Un mixte Lync Server 2010 et Skype pour le déploiement de Business Server 2015
- Un déploiement de Lync Server 2010 et Lync Server 2013 mixte
-   Un déploiement Lync Server 2010 avec tous les serveurs exécutant Lync Server 2010 avec les dernières mises à jour cumulatives.
La fédération Edge Server et le serveur du tronçon suivant de la fédération de serveur de transport Edge doivent exécuter Lync Server 2010 avec les dernières mises à jour cumulatives. Le Skype pour Business Server 2015 ou les outils d’administration de Lync Server 2013 doit être installé sur au moins un serveur ou station de travail de gestion.



 ## <a name="multi-forest-support"></a>Prise en charge des environnements multi-forêts
<a name="BKMK_MultiForest"> </a>

Les utilisateurs peuvent accéder aux fonctionnalités Skype Entreprise dans une autre forêt si les conditions suivantes sont réunies :

- Les utilisateurs sont correctement synchronisés dans la forêt qui héberge Skype Entreprise ; dans les configurations hybrides, cela signifie que les utilisateurs doivent être synchronisés en tant qu'objets utilisateurs désactivés.

- La forêt hébergeant Skype Entreprise doit approuver la forêt contenant les utilisateurs.

Pour plus d’informations sur les scénarios hybrides à forêts multiples, consultez [configurer un environnement à forêts multiples pour un environnement hybride Skype pour les entreprises](configure-a-multi-forest-environment-for-hybrid.md).


## <a name="federation-requirements"></a>Exigences de fédération
<a name="BKMK_Federation"> </a>

Lors de la configuration hybride, vous devez vous assurer que votre organisation locale et environnements online peuvent être fédéré avec eux.  L’environnement en ligne a fédération ouverte par défaut ; l’environnement local a souvent fermé fédération par défaut.  

La configuration ci-dessous est requise pour configurer un déploiement hybride :

- La correspondance de domaine doit être identique pour votre déploiement local et votre client Office 365. Si la découverte de partenaire est activée sur le déploiement local, la fédération ouverte doit être configurée pour votre client en ligne. Si la découverte de partenaire n'est pas activée, alors la fédération fermée doit être configurée pour votre client en ligne.

- La liste des domaines bloqués dans le déploiement local doit correspondre exactement à la liste des domaines bloqués pour votre client en ligne.

- La liste des domaines autorisés dans le déploiement local doit correspondre exactement à la liste des domaines autorisés pour votre client en ligne.

- Fédération doit être activée pour les communications externes pour le client en ligne.


## <a name="network-considerations"></a>Considérations relatives au réseau

Les sections suivantes décrivent les considérations relatives à : 

- Paramètres DNS 
- Éléments à prendre en compte pour le pare-feu 


### <a name="dns-settings"></a>Paramètres DNS
<a name="BKMK_DNS"> </a>

Lorsque vous créez des enregistrements DNS pour les déploiements hybrides, tous les Skype pour les enregistrements DNS externes Business doit pointer sur l’infrastructure locale. Pour plus d’informations sur les enregistrements DNS requis, reportez-vous à la [configuration DNS requise pour Skype pour Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

En outre, vous devez vous assurer que la résolution DNS décrite dans le tableau suivant fonctionne dans votre déploiement sur site. (Si vous déjà configuré la fédération pour locaux, puis probablement déjà avoir ces.)

|Enregistrement DNS  <br/> |Résolvable par  <br/> |Enregistrement DNS requis  <br/> |
|:-----|:-----|:-----|
|Enregistrement DNS SRV pour _sipfederationtls._tcp. \<sipdomain.com\> toutes prises en charge les domaines SIP résoudre les adresses IP externes Edge d’accès  <br/> |Serveur(s) Edge  <br/> |Permettre la communication fédérée dans une configuration hybride. Le serveur Edge doit savoir où acheminer le trafic fédéré pour le domaine SIP qui est à la fois en local et en ligne.  <br/> Doit utiliser un nom DNS strict identique pour le domaine du nom d'utilisateur et pour l'enregistrement SRV.  <br/> |
|Enregistrement(s) DNS A pour le FQDN du service de conférence web Edge, par exemple webcon.contoso.com se résolvant en adresse(s) IP externe(s) Edge de conférence web  <br/> |Réseau d’entreprise interne connecté les ordinateurs des utilisateurs  <br/> |Permettre aux utilisateurs de présenter ou d'afficher le contenu de réunions hébergées localement. Ce contenu peut inclure des fichiers PowerPoint, des tableaux blancs, des sondages et des notes partagées.   <br/> |

En fonction de la configuration DNS de votre organisation, vous devrez peut-être ajouter ces enregistrements dans la zone DNS hébergée en interne pour le(s) domaine(s) SIP correspondant(s) afin de fournir à ces enregistrements une résolution DNS interne. 

### <a name="firewall-considerations"></a>Éléments à prendre en compte pour le pare-feu
<a name="BKMK_Firewall"> </a>

Les ordinateurs du réseau doivent être en mesure d'effectuer des recherches DNS Internet. Si ces ordinateurs peuvent accéder à des sites Internet standard, votre réseau est correctement configuré.

Selon l’emplacement de votre centre de données Microsoft Online Services, vous devez également configurer vos périphériques de pare-feu réseau pour accepter les connexions basées sur des noms de domaine générique (par exemple, tout le trafic \*. outlook.com). Si le pare-feu de votre organisation ne prennent pas en charge les génériques des configurations de nom, vous devez déterminer manuellement les plages d’adresses IP que vous souhaitez autoriser et les ports spécifiés.

Pour plus d’informations, notamment des informations sur les ports et protocoles devant être, voir [Office 365 URL et plages d’adresses IP](https://go.microsoft.com/fwlink/p/?LinkId=252942).
