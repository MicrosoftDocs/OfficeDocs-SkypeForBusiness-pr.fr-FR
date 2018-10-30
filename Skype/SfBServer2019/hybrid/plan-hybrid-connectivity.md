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
ms.openlocfilehash: 17a54b4d7509684f5a74fd45549e3e0f9852a6c1
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838786"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Planification de la connectivité hybride entre Skype pour Business Server et Office 365

## <a name="overview"></a>Vue d’ensemble

Lisez cette rubrique pour savoir comment planifier la connectivité hybride entre Skype pour Business Server et Skype Business Online ou équipes. La première étape du déploiement de nombreuses solutions hybrides Skype Entreprise consiste à configurer une connectivité hybride.

Solutions hybrides permettent de conserver le contrôle sur site tout en bénéficiant des services en ligne fournis dans le nuage de Microsoft. Avec une variété de services en nuage disponibles pour votre site et les utilisateurs locaux et connectivité hybride configurer, vous pouvez choisir à déplacer les utilisateurs vers le nuage en fonction des besoins de votre calendrier et d’entreprise.

Par exemple, vous pouvez choisir d’obtenir le contrôle d’appel via le système téléphonique de Microsoft dans le nuage, tout en conservant votre une connectivité PSTN sur site. Vous pouvez également choisir tirer parti d’autres services en nuage, tels que la messagerie vocale dans le nuage et appeler de connecteur de données.

Cette rubrique décrit les spécifications système et infrastructure que nécessaires pour configurer la connectivité hybride entre votre Skype local existant pour le déploiement de Business Server--avec des utilisateurs qui ont été créés dans votre Active Directory--sur site et Skype pour les professionnels en ligne ou équipes.

Une fois que vous avez lu cet article et que vous êtes prêt à configurer la connectivité hybride, consultez [configurer la connectivité hybride entre Skype pour Business Server et Office 365](configure-hybrid-connectivity.md). Les rubriques de configuration fournissent des instructions détaillées pour la configuration de la connectivité hybride entre votre déploiement sur site et de Skype pour Business en ligne.

(Pour plus d’informations sur la configuration de votre déploiement de Lync Server 2010 pour l’environnement hybride ou de Lync Server 2013, voir [Lync Server 2013 hybride](https://go.microsoft.com/fwlink/p/?LinkId=617360)).

## <a name="split-domain-functionality"></a>Fonctionnalité de domaine fractionné
<a name="BKMK_Overview"> </a>

 Connectivité hybride configuré entre un déploiement local de Skype pour Business Server et Skype pour Business Online ou équipes, vous pouvez avoir certains utilisateurs hébergés sur un système local et certains utilisateurs hébergement en ligne.

Ce type de configuration est parfois appelé « domaine fragmenté », ce qui signifie que les utilisateurs d’un domaine, par exemple, contoso.com, sont répartis entre à l’aide de Skype pour Business Server localement et Skype pour Business Online ou équipes, comme illustré dans le diagramme suivant :

![Connectivité hybride SfB - domaine partagé](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Avec un environnement de domaine fractionné :

- Les utilisateurs qui sont hébergés sur site interagissent avec Skype locaux des serveurs d’entreprise. Ils peuvent également avoir accès aux services en ligne, telles que la messagerie vocale dans le nuage.

- Les utilisateurs hébergés en ligne peuvent interagir avec Skype pour les services en ligne équipes ou de l’entreprise.

- Les utilisateurs à partir des deux environnements peuvent collaborer avec eux à l’aide de la messagerie instantanée, participation à des téléconférences ou les appels VoIP et ainsi de suite.

- Azure Active Directory se connecter permet de synchroniser votre annuaire local avec Office 365.

Active Directory fait autorité, procédez donc comme indiqué ci-après pour permettre la détection entre les utilisateurs sur site et en ligne :

- Tous les utilisateurs doivent être créés dans Active Directory local en premier et puis synchronisés avec Azure AD.

- Les utilisateurs qui sont déplacés vers le nuage doivent avoir soit Skype une licence entreprise Plan 2 ou équipes.

- Si vous souhaitent que vos utilisateurs à tirer parti des fonctionnalités en ligne supplémentaires, tels que Skype diffusion de réunion ou de la messagerie vocale dans le nuage, vous devez affecter la licence appropriée dans Office 365.

- Une fois la licence Skype Entreprise Online affectée aux utilisateurs, vous devez les activer pour Skype Entreprise ou pour Voix Entreprise sur site. Pour plus d’informations, voir [Activer les utilisateurs pour Enterprise Voice sur site](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises.md). Pour plus d'informations sur les conditions requises pour la solution vocale hybride, reportez-vous à l'article [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md).


## <a name="infrastructure-requirements"></a>Conditions requises pour l'infrastructure
<a name="BKMK_Infrastructure"> </a>

Pour implémenter la connectivité hybride entre votre environnement local et les services de communication Office 365, vous devez remplir les conditions d’infrastructure suivantes.

- Un seul déploiement local de Skype pour Business Server ou un serveur Lync qui est déployé dans une topologie prise en charge. Dans cette rubrique, voir [Configuration requise de topologie](plan-hybrid-connectivity.md#BKMK_Topology) .

- Un client Microsoft Office 365 avec Skype pour Business Online activé.

    > [!NOTE]
    > Vous ne pouvez utiliser qu'un seul client pour une configuration hybride avec votre déploiement local.

- Skype pour les outils d’administration Business Server. (Si vous utilisez Lync Server 2013 ou Lync Server 2010, vous pouvez utiliser les outils d’administration Lync Server 2013. Pour plus d'informations, reportez-vous à l'article [Lync Server 2013 hybride](https://go.microsoft.com/fwlink/p/?LinkId=617360).

- Azure Active Directory Connect pour synchroniser votre répertoire sur site avec Office 365. Pour plus d’informations, voir [Azure AD Connect : comptes et autorisations](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

    Pour prendre en charge l'authentification unique Office 365 afin que les utilisateurs puissent utiliser les mêmes informations d'identification de connexion sur site, vous pouvez utiliser les fonctionnalités de synchronisation des mots de passe Azure Active Directory (AAD) Connect. Vous pouvez également utiliser AD FS (Active Directory Federation Services) avec l’authentification unique pour Office 365. 

Pour configurer la connectivité hybride, vous devez également configurer la fédération entre votre organisation locale et environnements en ligne et de configurer votre Skype pour Business Online client pour un espace d’adressage partagé protocole SIP (Session Initiation). Pour plus d’informations sur les étapes nécessaires pour configurer la connectivité hybride, voir [connectivité de configuration hybride](configure-hybrid-connectivity.md).

Après avoir configuré la connectivité hybride, vous pouvez déplacer des utilisateurs à Skype pour Business Online ou équipes. Pour plus d’informations, voir [déplacer des utilisateurs à partir de sur site à Skype pour Business Online](move-users-from-on-premises-to-skype-for-business-online.md) et [déplacer les utilisateurs sur site aux équipes](move-users-from-on-premises-to-teams.md).

## <a name="multi-forest-support"></a>Prise en charge des environnements multi-forêts
<a name="BKMK_MultiForest"> </a>

Les utilisateurs peuvent accéder aux fonctionnalités Skype Entreprise dans une autre forêt si les conditions suivantes sont réunies :

- Les utilisateurs sont correctement synchronisés dans la forêt qui héberge Skype Entreprise ; dans les configurations hybrides, cela signifie que les utilisateurs doivent être synchronisés en tant qu'objets utilisateurs désactivés.

- La forêt hébergeant Skype Entreprise doit approuver la forêt contenant les utilisateurs.

Pour plus d’informations sur les scénarios hybrides à forêts multiples, consultez [configurer un environnement à forêts multiples pour un environnement hybride Skype pour les entreprises](configure-a-multi-forest-environment-for-hybrid.md).

## <a name="administrator-credentials"></a>Informations d'identification de l'administrateur
<a name="BKMK_Credentials"> </a>

Lorsque vous êtes invité à fournir vos informations d’identification d’administrateur, utilisez le nom d’utilisateur et le mot de passe pour le compte d’administrateur pour votre client Office 365. Vous allez également utiliser ces informations d’identification lorsque vous configurez Azure Active Directory pour la fédération, la synchronisation d’annuaires, authentification unique et déplacement d’utilisateurs vers Skype pour Business en ligne.

## <a name="skype-for-business-online-powershell"></a>Skype Entreprise Online PowerShell
<a name="BKMK_PowerShell"> </a>

Les administrateurs ont désormais la possibilité d’utiliser Windows PowerShell pour gérer Skype pour Business Online et leur Skype pour les comptes d’utilisateurs professionnels en ligne. Pour ce faire, vous devez d’abord télécharger et installer le Skype pour Module connecteur en ligne d’entreprise à partir du Microsoft Download Center. Pour plus d’informations sur le téléchargement, l’installation et à l’aide de la Skype pour Module connecteur en ligne d’entreprise et pour plus d’informations sur l’utilisation de Windows PowerShell pour gérer Skype pour Business Online, voir [configurer votre ordinateur pour Windows PowerShell](https://technet.microsoft.com/library/dn362831.aspx).

## <a name="skype-for-business-client-support"></a>Prise en charge du client Skype Entreprise
<a name="BKMK_ClientSupport"> </a>

Des différences existent dans les fonctionnalités prises en charge dans les clients, ainsi que dans les fonctionnalités disponibles dans des environnements locaux et en ligne. Les clients suivants sont pris en charge avec Skype pour Business Online dans un déploiement hybride :

- Skype Entreprise

- Lync 2013

- Lync 2010

- application Lync du Windows Store

- Lync Web App

- Lync Mobile

- Lync pour Mac 2011

- Système de salle de Lync et Skype pour le système d’entreprise salle

- Lync Basic 2013

- Microsoft Surface Hub

Avant de décider où vous souhaitez héberger des utilisateurs dans votre organisation, vous devez examiner la [comparaison des fonctionnalités client de bureau pour Skype pour les entreprises](../../sfbserver/plan-your-deployment/clients-and-devices/desktop-feature-comparison.md) pour déterminer la prise en charge du client pour les différentes configurations de Skype pour Business Server. Voir aussi :

- [Planifier des clients et des appareils](../../sfbserver/plan-your-deployment/clients-and-devices/clients-and-devices.md)

- [Comparaison des fonctionnalités de client mobile pour Skype pour les entreprises](../../sfbserver/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)

## <a name="topology-requirements"></a>Conditions requises pour la topologie
<a name="BKMK_Topology"> </a>

Pour configurer votre déploiement hybride avec Skype pour Business Online, vous devez disposer d’un des topologies prises en charge suivantes :

- Un Skype pour le déploiement d’entreprise Server 2015 avec tous les serveurs exécutant Skype pour Business Server 2015.

- Un déploiement de Lync Server 2013 avec tous les serveurs exécutant Lync Server 2013.

    Pour la connectivité de voix hybride, le serveur de périphérie est désigné comme serveur Edge de fédération doit être Skype pour Business 2015 ; le bord requiert également une Skype pour Business Server principal. Vous pouvez disposer d'un pool sans utilisateur.

- Un déploiement Lync Server 2010 avec tous les serveurs exécutant Lync Server 2010 avec les dernières mises à jour cumulatives.

  - La fédération Edge Server et le serveur du tronçon suivant de la fédération de serveur de transport Edge doivent exécuter Lync Server 2010 avec les dernières mises à jour cumulatives.

  - Le Skype pour Business Server 2015 ou les outils d’administration de Lync Server 2013 doit être installé sur au moins un serveur ou station de travail de gestion.

- Lync Server 2013 et Skype pour le déploiement de Business Server 2015 avec les rôles de serveur suivants au moins un site exécutant Skype pour Business Server 2015 mixte :

  - Au moins un pool d'entreprise ou serveur Standard Edition 

  - Pool directeur associé à la fédération SIP, le cas échéant

  - Pool Edge associé à la fédération SIP

- Lync Server 2010 et Skype pour le déploiement de Business Server 2015 avec les rôles de serveur suivants au moins un site exécutant Skype pour Business Server 2015 mixte :

  - Au moins un pool d'entreprise ou serveur Standard Edition 

  - Pool directeur associé à la fédération SIP, le cas échéant

  - Pool Edge associé à la fédération SIP pour le site

- Un déploiement de Lync Server 2010 et Lync Server 2013 mixte avec les rôles de serveur suivants au moins un site exécutant Lync Server 2013 :

  - Au moins un pool d'entreprise ou serveur Standard Edition dans le site

  - Pool directeur associé à la fédération SIP, si elle existe dans le site

  - Pool Edge associé à la fédération SIP pour le site

## <a name="federation-allowedblocked-lists-requirements"></a>Configuration requise pour les listes de fédération autorisées/bloquées
<a name="BKMK_Federation"> </a>

La liste des domaines autorisés inclut les domaines qui ont un nom de domaine complet de serveur Edge partenaire (FQDN) configuré. Ceux-ci sont parfois appelés serveurs partenaire autorisé ou diriger les partenaires de la fédération. Vous devez connaître la différence entre la fédération ouverte et fermée la fédération, appelé découverte des partenaires et liste de domaine partenaire autorisé, respectivement, dans les déploiements sur site.

La configuration ci-dessous est requise pour configurer un déploiement hybride :

- La correspondance de domaine doit être identique pour votre déploiement local et votre client Office 365. Si la découverte de partenaire est activée sur le déploiement local, la fédération ouverte doit être configurée pour votre client en ligne. Si la découverte de partenaire n'est pas activée, alors la fédération fermée doit être configurée pour votre client en ligne.

- La liste des domaines bloqués dans le déploiement local doit correspondre exactement à la liste des domaines bloqués pour votre client en ligne.

- La liste des domaines autorisés dans le déploiement local doit correspondre exactement à la liste des domaines autorisés pour votre client en ligne.

- Fédération doit être activée pour les communications externes pour le client en ligne, qui est configurée à l’aide de la Skype pour Business Online le panneau de configuration.

## <a name="dns-settings"></a>Paramètres DNS
<a name="BKMK_DNS"> </a>

Lorsque vous créez des enregistrements DNS pour les déploiements hybrides, tous les Skype pour les enregistrements DNS externes Business doit pointer sur l’infrastructure locale. Pour plus d’informations sur les enregistrements DNS requis, reportez-vous à la [configuration DNS requise pour Skype pour Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

En outre, vous devez vous assurer que la résolution DNS décrite dans le tableau suivant fonctionne dans votre déploiement sur site :

|Enregistrement DNS  <br/> |Résolvable par  <br/> |Enregistrement DNS requis  <br/> |
|:-----|:-----|:-----|
|Enregistrement DNS SRV pour _sipfederationtls._tcp. \<sipdomain.com\> toutes prises en charge les domaines SIP résoudre les adresses IP externes Edge d’accès  <br/> |Serveur(s) Edge  <br/> |Permettre la communication fédérée dans une configuration hybride. Le serveur Edge doit savoir où acheminer le trafic fédéré pour le domaine SIP qui est à la fois en local et en ligne.  <br/> Doit utiliser un nom DNS strict identique pour le domaine du nom d'utilisateur et pour l'enregistrement SRV.  <br/> |
|Enregistrement(s) DNS A pour le FQDN du service de conférence web Edge, par exemple webcon.contoso.com se résolvant en adresse(s) IP externe(s) Edge de conférence web  <br/> |Réseau d’entreprise interne connecté les ordinateurs des utilisateurs  <br/> |Permettre aux utilisateurs de présenter ou d'afficher le contenu de réunions hébergées localement. Ce contenu peut inclure des fichiers PowerPoint, des tableaux blancs, des sondages et des notes partagées.   <br/> |

En fonction de la configuration DNS de votre organisation, vous devrez peut-être ajouter ces enregistrements dans la zone DNS hébergée en interne pour le(s) domaine(s) SIP correspondant(s) afin de fournir à ces enregistrements une résolution DNS interne.

## <a name="firewall-considerations"></a>Éléments à prendre en compte pour le pare-feu
<a name="BKMK_Firewall"> </a>

Les ordinateurs du réseau doivent être en mesure d'effectuer des recherches DNS Internet. Si ces ordinateurs peuvent accéder à des sites Internet standard, votre réseau est correctement configuré.

Selon l’emplacement de votre centre de données Microsoft Online Services, vous devez également configurer vos périphériques de pare-feu réseau pour accepter les connexions basées sur des noms de domaine générique (par exemple, tout le trafic \*. outlook.com). Si le pare-feu de votre organisation ne prennent pas en charge les génériques des configurations de nom, vous devez déterminer manuellement les plages d’adresses IP que vous souhaitez autoriser et les ports spécifiés.

Pour plus d'informations, reportez-vous à la rubrique [URL et plages d'adresses IP Office 365](https://go.microsoft.com/fwlink/p/?LinkId=252942).

## <a name="port-and-protocol-requirements"></a>Configuration requise pour les ports et les protocoles
<a name="BKMK_Ports"> </a>

En plus de la configuration requise pour les ports pour les communications internes, vous devez également configurer les ports suivants pour activer la connectivité hybride :


|**Protocole**|**TCP ou UDP**|**Adresse IP source**|**Adresse IP de destination**|**Port source**|**Port de destination**|**Remarques**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|SIP (MTLS)  <br/> |TCP  <br/> |Serveur Edge d’accès  <br/> |Office 365  <br/> |Indifférente  <br/> |5061  <br/> |Signalisation  <br/> |
|SIP (MTLS)  <br/> |TCP  <br/> |Office 365  <br/> |Serveur Edge d’accès  <br/> |Indifférente  <br/> |5061  <br/> |Signalisation  <br/> |
|STUN  <br/> |TCP  <br/> |Edge A/V  <br/> |Office 365  <br/> |50000-59999  <br/> |443, 50000-59999  <br/> |Ouvrir pour les sessions audio, vidéo et de partage d'applications  <br/> |
|STUN  <br/> |TCP  <br/> |Office 365  <br/> |Edge A/V  <br/> |443  <br/> |50000-59999  <br/> |Ouvrir pour les sessions audio, vidéo et de partage d'applications  <br/> |
|STUN  <br/> |UDP  <br/> |Edge A/V  <br/> |Office 365  <br/> |3478  <br/> |3478  <br/> |Ouvrir pour les sessions audio, vidéo  <br/> |
|STUN  <br/> |UDP  <br/> |Office 365  <br/> |Edge A/V  <br/> |3478  <br/> |3478  <br/> |Ouvrir pour les sessions audio, vidéo  <br/> |

Pour plus d’informations sur le port et de planification pour le serveur Edge de pare-feu, consultez [exigences de serveur de transport Edge dans Skype pour Business Server](../../sfbserver/plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md). Reportez-vous également à l'article [Port and protocol requirements for servers](../../sfbserver/plan-your-deployment/network-requirements/ports-and-protocols.md) et au [Digramme des charges de travail de protocole](https://go.microsoft.com/fwlink/p/?LinkId=550989).

## <a name="user-accounts-and-data"></a>Comptes et données utilisateur
<a name="BKMK_UserAccounts"> </a>

Dans un déploiement hybride, n’importe quel utilisateur vous autorisez à domicile en ligne doit être créé dans le déploiement local, afin que le compte d’utilisateur est créé dans Active Directory Domain Services. Vous pouvez ensuite déplacer l’utilisateur à Skype pour Business en ligne, qui déplace la liste des contacts de l’utilisateur.

Lorsque vous synchronisez les comptes d’utilisateurs entre votre déploiement local et du client en ligne à l’aide de DAS se connecter, vous devez synchroniser les comptes Active Directory pour tous les Skype pour les utilisateurs de Lync ou de l’entreprise dans votre organisation, même si les utilisateurs ne sont pas déplacés vers en ligne. Si vous ne synchronisez pas tous les utilisateurs, la communication entre les utilisateurs locaux et en ligne dans votre organisation risque de ne pas fonctionner comme vous le souhaitez.

> [!IMPORTANT]
> Gestion de tous les utilisateurs, y compris utilisateur déplace entre locale et Skype pour Business Online doivent être effectué à l’aide de la dernière version installée des outils d’administration. Les outils d’administration doivent être installés sur un serveur distinct qui a un accès de connexion pour le déploiement local existant et Internet. L’applet de commande pour déplacer les utilisateurs de votre déploiement sur site vers Skype pour Business Online, [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps), doit être exécuté à partir des outils d’administration connectées à votre déploiement sur site. Pour plus d’informations sur le déplacement d’utilisateurs, voir [déplacer des utilisateurs à partir de sur site à Skype pour Business Online](move-users-from-on-premises-to-skype-for-business-online.md).

Vous devez également tenir compte les problèmes suivants relatifs à l’utilisateur lors de la planification d’un déploiement hybride :

- **Contacts de l’utilisateur** La limite des contacts pour les utilisateurs de Lync Online est de 250. Les contacts au-delà de ce numéro seront retirés liste des contacts de l’utilisateur lorsque le compte est déplacé vers Lync Online.

- **Messagerie instantanée et présence** Listes des contacts utilisateur, des groupes et des listes de contrôle d’accès (ACL) sont migrées avec le compte d’utilisateur.

- **Données de conférence, contenu de réunion et les réunions planifiées** Ce contenu n’est pas migré avec le compte d’utilisateur. Les utilisateurs doivent replanifier les réunions une fois leur compte migré sur Lync Online.

## <a name="user-policies-and-features"></a>Fonctionnalités et stratégies utilisateur
<a name="BKMK_UserPolicies"> </a>

- Dans un environnement hybride, les utilisateurs peuvent utiliser la messagerie instantanée et les réunions soit sur site soit en ligne, mais pas les deux simultanément.

- **Prise en charge du client** Certains utilisateurs peuvent nécessiter une nouvelle version de client lorsqu’ils sont déplacés vers Skype pour Business Online. Pour Office Communications Server 2007 R2, les utilisateurs doivent être déplacés vers un Skype pour Business Server ou Microsoft Lync Server 2013 pool avant la migration vers Skype pour Business Online.

- **Configuration (non utilisateur) et les stratégies local** En ligne et locales stratégies nécessitent une configuration distincte. Vous ne pouvez pas définir des stratégies globales qui s'appliquent au deux.
