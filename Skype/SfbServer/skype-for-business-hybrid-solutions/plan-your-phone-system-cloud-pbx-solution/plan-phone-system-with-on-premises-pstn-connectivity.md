---
title: Planifier Business Server système téléphonique dans Office 365 avec une connectivité PSTN local dans Skype
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: Obtenir des informations sur les considérations de planification pour le système téléphonique dans Office 365 (en nuage PBX) avec une connectivité PSTN sur site.
ms.openlocfilehash: f0e73b2541bdab8d3e37db02bc023667ae942578
ms.sourcegitcommit: d12a9f2d10093e24d4af54ce6044b512e7e3787e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454042"
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Planifier Business Server système téléphonique dans Office 365 avec une connectivité PSTN local dans Skype

Obtenir des informations sur les considérations de planification pour le système téléphonique dans Office 365 (en nuage PBX) avec une connectivité PSTN sur site.

Ce contenu est utile si vous avez déjà Skype pour Business Server ou Microsoft Lync Server 2013 déployés en local. Pour d’autres scénarios, voir [solutions de téléphonie Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions).

 Système téléphonique dans Office 365 avec une connectivité PSTN sur site vous permet de bénéficier de fonctionnalités du système téléphonique (PBX nuage) pour vos utilisateurs. Cela peut vous être utile dans les scénarios suivants :

- Vous avez certains de vos Skype pour Business les utilisateurs hébergés sur un système local et d’autres utilisateurs hébergement dans Skype pour Business Online. Vous pouvez maintenant activer le système téléphonique dans Office 365 capacités et fonctionnalités pour vos utilisateurs hébergement dans Skype pour Business Online, mais continuent à utiliser une connectivité PSTN sur site.

- Vous disposez d’un déploiement sur site et que vous souhaitez déplacer tout ou partie de vos utilisateurs à Skype pour Business Online mais continuer à utiliser une connectivité PSTN sur site.

    > [!IMPORTANT]
    > Pour activer correctement les utilisateurs pour le système téléphonique dans Office 365 avec une connectivité PSTN sur site, leur adresse SIP doit être dans votre domaine. L'utilisation du domaine par défaut pour Office 365, onmicrosoft.com, n'est pas prise en charge. 

Pour en savoir plus sur le système téléphonique dans Office 365, notamment la gestion des licences et plans, voir [appel PSTN de plans de Skype pour les entreprises](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).

## <a name="feature-comparison"></a>Comparaison des fonctionnalités

Nuage PBX avec une connectivité PSTN local n’offre pas la même fonctionnalité à définir en tant qu’une solution de voix entreprise entièrement locale. Pour vous aider à décider si PBX dans le nuage avec une connectivité PSTN local fournit la fonctionnalité définies pour votre organisation, voir [Voici ce que vous obtenez avec PBX dans le nuage](https://go.microsoft.com/fwlink/?LinkId=715517).

## <a name="benefits-and-planning-considerations"></a>Avantages et points à prendre en compte en matière de planification

> [!CAUTION]
> Les appareils Lync Phone Edition DOIVENT être mis à jour vers les microprogrammes minimaux requis dans votre environnement local AVANT de passer à Skype Entreprise Online.
Si vous transférez les utilisateurs de votre déploiement local à la solution en ligne avant la mise à jour du microprogramme, les utilisateurs ne pourront pas se connecter en utilisant leur téléphone. Pour résoudre ce problème, les utilisateurs doivent être transférés à nouveau vers l’environnement local pour que leur téléphone soit mis à jour avec le microprogramme minimal requis. N’ESSAYEZ PAS DE METTRE À JOUR LE MICROPROGRAMME MINIMAL REQUIS OU D’EFFECTUER UNE MISE À JOUR MATÉRIELLE DE VOTRE TÉLÉPHONE AVANT DE REDÉPLACER L’UTILISATEUR VERS VOTRE ENVIRONNEMENT LOCAL.
Si une réinitialisation matérielle est effectuée alors que la version minimale du microprogramme n’est pas installée sur l’appareil, il utilisera par défaut l’authentification par code confidentiel, qui n’est pas prise en charge dans Skype Entreprise Online. Pour plus d’informations, reportez-vous aux [téléphones mise en route pour Skype pour Business Online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).

En déployant le système téléphonique dans Office 365 avec une connectivité PSTN sur site, vous pouvez déplacer vos utilisateurs vers le nuage via Skype pour Business en ligne à votre rythme, tout en conservant la connectivité PSTN sur site. Si vous disposez d'un PBX, continuez à l'utiliser pour fournir une connectivité PSTN aux utilisateurs que vous transférez vers le cloud. Une fois qu’un utilisateur est déplacé vers Skype pour Business Online et système téléphonique dans Office 365, leur téléphone PBX existant ne fonctionne plus, mais son numéro de téléphone acheminera à n’importe lequel de la Skype pour les clients d’entreprise pour PC ou Smartphones ainsi que Skype pour téléphone de bureau compatibles Business s. Une fois que les ports, système téléphonique dans les utilisateurs Office 365 et PBX hérité peuvent s’appellent normalement ainsi émettre et recevoir des appels PSTN à l’aide de son numéro de téléphone normal.

Vous pouvez disposer d'une fonctionnalité personnalisée ou d'un composant supplémentaire important pour votre PBX hérité, comme un centre d'appels. Si la fonction personnalisée n’est pas actuellement disponible sur le système téléphonique dans Office 365, vous devez laisser les utilisateurs qui nécessitent cette fonctionnalité personnalisé local avec le PBX hérités et le port que les utilisateurs qui n’ont pas besoin d’accéder à la fonctionnalité personnalisée au système téléphonique dans Office 365 avec une connectivité PSTN sur site.

Pour obtenir une liste de PBX hérité qui interagissent directement avec Skype pour Business Server 2015 voir [Complet de l’Infrastructure pour Microsoft Lync](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway). Si votre système PBX ne se trouve pas dans cette liste, vous pouvez utiliser un contrôleur de Session en périphérie pour connecter votre système PBX avec un système téléphonique dans Office 365 dans Skype pour Business Online.

### <a name="network-considerations-for-quality-and-performance"></a>Considérations relatives au réseau pour la qualité et les performances

Lors du déploiement d’un service hébergé sur le nuage comme système téléphonique dans Office 365 avec une connectivité PSTN sur site, vous devez gardez les points suivants à l’esprit. Dans un Skype purement locaux pour le déploiement de Business Server 2015 Enterprise Voice, tous les clients et l’infrastructure sont sur le réseau d’entreprise. La qualité et les performances de ce réseau, qui sont essentielles pour obtenir un son et une image de bonne qualité, sont contrôlées directement par le personnel de l'entreprise. Système téléphonique dans Office 365 avec une connectivité PSTN sur site, il existe trois réseaux impliqués, dont le client est responsable des deux mais seul dont le personnel de l’entreprise a un contrôle direct :

- **Réseau de distribution de média globales de Microsoft** Réseau de nuage global et l’infrastructure de Microsoft. Office 365 et système téléphonique dans le trafic et les serveurs Office 365 parcourent ce réseau.

- **Entreprise/de nuage PSTN Interconnect** Il s’agit du réseau qui connecte votre entreprise vers le nuage Office 365. Il n'est pas forcément identique à votre connexion Internet générique.

- **Votre réseau d’entreprise** La qualité des médias en temps réel dépend fortement de votre propre réseau : en particulier du réseau Wi-Fi et la qualité de l’interconnexion utilisée pour atteindre le nuage Office 365.

> [!NOTE]
> Pour plus d’informations sur le réglage des performances dans Skype pour Business Online, voir [Skype de réglage des performances métiers en ligne](https://support.office.com/en-us/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US). 

## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Conditions requises pour utiliser le système téléphonique dans Office 365 avec une connectivité PSTN sur site

Avant de pouvoir configurer système téléphonique dans Office 365 avec une connectivité PSTN local et déplacer les utilisateurs vers Skype pour Business Online, vous devez confirmer que vous disposez les conditions préalables suivantes :

 **Versions de serveur local.** Les versions des serveurs de votre déploiement sur site doivent figurer dans le tableau suivant pour prendre en charge un système téléphonique dans Office 365 avec une connectivité PSTN sur site.


| **Rôle serveur**                                       | **Versions prises en charge\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Fédération Edge\*\*  <br/>                            | Skype Entreprise Server 2015  <br/>                                                                              |
| Serveur de pool interne de l'itinéraire de fédération pour le tronçon suivant  <br/> | Skype Entreprise Server 2015, mise à jour cumulative 6.0.9319.235 de mars 2016 ou version ultérieure (Frontal ou Directeur)   <br/> |
| Serveur frontal de l'utilisateur  <br/>                          | Skype Entreprise Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Serveur Edge  <br/>                                    | Skype Entreprise Server 2015  <br/>                                                                              |
| serveur de médiation  <br/>                               | Skype Entreprise Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*Configuration minimale des versions prises en charge sont les suivants :

- Skype Entreprise Server 2015, mise à jour cumulative 6.0.9319.235 de mars 2016

- Lync Server 2013, mise à jour cumulative 5.0.8308.920 de juillet 2015

\*\*La fédération de routage pour tous les domaines SIP pris en charge doivent repositionner la Skype pour l’exécution du serveur de périphérie Business Server 2015 mise à jour Cumulative des mars 2016 ou version ultérieure. Si le pool d'utilisateurs se trouve sur Lync Server 2013, le trafic de pool externe reste sur le serveur Edge de Lync Server 2013. 

En outre, vous devez vérifier les éléments suivants :

- **On-premises Enterprise Voice est configuré et testé pour les utilisateurs locaux** Cela inclut les composants de connectivité PSTN. Pour plus d’informations, consultez les rubriques suivantes si vous utilisez Skype pour Business Server 2015, voir [Planifier pour Enterprise Voice sur Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) et [Déployer Enterprise Voice dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Si vous utilisez Lync Server 2013, voir [planification de voix entreprise dans Lync Server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) et le [Déploiement d’Enterprise Voice dans Lync Server 2013](https://technet.microsoft.com/EN-US/library/gg412876%28v=ocs.15%29.aspx).

- **Synchronisation Active Directory** Vous devez configurer la synchronisation Active Directory à l’aide d’Azure AD se connecter. Pour plus d'informations, reportez-vous à [Gestion d'Azure AD Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/).

    > [!NOTE]
    > La version AAD Connect que vous utilisez doit être la version 1.0.9125.0 ou une version ultérieure. Si vous utilisez des outils d'une version antérieure d'AAD Connect ou de DirSync, effectuez une mise à niveau vers la version prise en charge. Vous pouvez mettre à niveau votre installation actuelle et conserver les règles personnalisées définies dans votre environnement. 

- **Configurer votre déploiement hybride** Si tous vos Skype pour les utilisateurs professionnels sont actuellement hébergement soit en ligne ou sur site, ou si vous avez actuellement une combinaison, vous devez effectuer les étapes pour configurer un déploiement hybride de Skype pour Business Server ou de Lync Server 2013, comme indiqué dans [Déploiement hybride connectivité entre Skype pour Business Server et Office 365](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md). Pour plus d’informations sur les déploiements hybrides, voir [planification de la connectivité hybride entre Skype pour Business Server et Office 365](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). 

    Si vous utilisez Lync Server 2013, voir [Lync Server 2013 hybrid](https://technet.microsoft.com/EN-US/library/jj204805%28v=ocs.15%29.aspx).

- **Active Directory Federation Services (ADFS) (recommandé)** Nous vous recommandons de déployer AD FS pour prendre en charge de l’authentification unique. Pour plus d’informations, voir [Active Directory Federation Services (ADFS)](https://technet.microsoft.com/en-us/library/cc736690%28v=ws.10%29.aspx).

Pour plus d’informations sur le déploiement du système téléphonique dans Office 365, voir [Activer les utilisateurs pour le système téléphonique dans Office 365 avec une connectivité PSTN dans Skype pour Business Server local](enable-users-for-phone-system.md).


