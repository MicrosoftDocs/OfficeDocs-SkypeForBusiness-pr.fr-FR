---
title: Planifier le système téléphonique dans Office 365 avec une connectivité RTC locale dans Skype entreprise Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: Découvrez les considérations relatives à la planification du système téléphonique dans Office 365 (Cloud PBX) avec une connectivité RTC locale.
ms.openlocfilehash: be8fbe5671e2959341c08d4efa45829df0cc5e42
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42020225"
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Planifier le système téléphonique dans Office 365 avec une connectivité RTC locale dans Skype entreprise Server

Découvrez les considérations relatives à la planification du système téléphonique dans Office 365 (Cloud PBX) avec une connectivité RTC locale.

Ce contenu est pertinent si vous avez déjà déployé Skype entreprise Server ou Lync Server 2013 en local. Pour d’autres scénarios, consultez la rubrique [solutions de téléphonie Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions).

 Le système téléphonique dans Office 365 avec une connectivité RTC locale vous permet d’utiliser les fonctionnalités de système téléphonique (PBX Cloud) pour vos utilisateurs. Cela peut vous aider dans les scénarios suivants :

- Certains de vos utilisateurs de Skype entreprise sont hébergés en local et d’autres dans Skype entreprise online. Vous pouvez désormais activer le système téléphonique dans Office 365 fonctionnalités et fonctionnalités pour vos utilisateurs hébergés dans Skype entreprise Online, mais continuer à utiliser la connectivité RTC locale.

- Vous disposez d’un déploiement local et vous souhaitez déplacer une partie ou la totalité de vos utilisateurs vers Skype entreprise Online, mais continuer à utiliser la connectivité RTC locale.

    > [!IMPORTANT]
    > Pour activer les utilisateurs pour le système téléphonique dans Office 365 avec une connectivité RTC locale, leur adresse SIP doit se trouver dans votre propre domaine. L’utilisation du domaine par défaut pour Office 365, onmicrosoft.com, n’est pas prise en charge. 

Pour en savoir plus sur le système téléphonique dans Office 365, y compris les licences et les plans, voir [RTC Calling forfaits for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).

## <a name="feature-comparison"></a>Comparaison des fonctionnalités

Le PBX Cloud avec connectivité RTC locale n’offre pas le même ensemble de fonctionnalités qu’une solution voix entreprise entièrement locale. Pour vous aider à déterminer si le PBX Cloud avec connectivité RTC locale fournit le jeu de fonctionnalités approprié à votre organisation, consultez les [informations ci-dessous](https://go.microsoft.com/fwlink/?LinkId=715517)sur le système PBX Cloud.

## <a name="benefits-and-planning-considerations"></a>Avantages et considérations sur la planification

> [!CAUTION]
> Les appareils Lync Phone Edition doivent être mis à jour vers le microprogramme minimal requis dans votre environnement local avant de passer à Skype entreprise online.
Si vous déplacez vos utilisateurs de la version locale vers la version en ligne avant de mettre à jour le microprogramme, les utilisateurs ne pourront pas se connecter à l’aide de leur téléphone. Pour corriger ce problème, les utilisateurs doivent être déplacés vers l’environnement local pour que leur téléphone soit mis à jour avec le microprogramme minimal. N’ESSAYEZ PAS DE METTRE À JOUR LE MICROPROGRAMME MINIMAL OU LA RÉINITIALISATION MATÉRIELLE DU TÉLÉPHONE AVANT DE REPLACER L’UTILISATEUR DANS VOTRE ENVIRONNEMENT LOCAL.
Si une réinitialisation matérielle est effectuée alors que le périphérique n’est pas au minimum de microprogramme, il utilisera par défaut l’authentification par code confidentiel, ce qui n’est pas pris en charge dans Skype entreprise online. Pour plus d’informations, reportez-vous à la rubrique [obtention de numéros de téléphone pour Skype entreprise Online](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).

En déployant le système téléphonique dans Office 365 avec une connectivité RTC locale, vous pouvez déplacer vos utilisateurs vers le Cloud via Skype entreprise Online à votre rythme, tout en conservant leur connectivité RTC locale. Si vous disposez d’un PBX, vous continuez à l’utiliser pour fournir une connectivité PSTN aux utilisateurs que vous déplacez dans le Cloud. Une fois qu’un utilisateur est déplacé vers Skype entreprise Online et le système téléphonique dans Office 365, son téléphone PBX hérité ne fonctionne plus, mais son numéro de téléphone est acheminé vers l’un des clients Skype entreprise pour des PC ou des téléphones intelligents, ainsi que pour un téléphone de bureau compatible Skype entreprise. ›. Une fois portés, le système téléphonique dans Office 365 les utilisateurs et les utilisateurs PBX hérités peuvent se téléphoner normalement et établir/recevoir des appels RTC à l’aide de leur numéro de téléphone normal.

Vous disposez peut-être d’une fonctionnalité personnalisée ou d’un complément principal sur votre système PBX hérité, tel qu’un centre d’appels. Si la fonctionnalité personnalisée n’est actuellement pas disponible sur le système téléphonique dans Office 365, vous devez laisser ces utilisateurs qui ont besoin de cette fonctionnalité personnalisée sur site avec le PBX hérité, et uniquement transférer les utilisateurs qui n’ont pas besoin d’accéder à la fonctionnalité personnalisée vers le système téléphonique dans Office 365 avec une connectivité RTC locale.

Pour obtenir la liste des PBX hérités qui interagissent directement avec Skype entreprise Server 2015, voir [infrastructure Qualified for Microsoft Lync](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway). Si votre PBX ne figure pas sur cette liste, vous pouvez utiliser un contrôleur de frontière de session pour connecter votre système PBX avec le système téléphonique dans Office 365 dans Skype entreprise online.

### <a name="network-considerations-for-quality-and-performance"></a>Considérations relatives au réseau pour la qualité et les performances

Lorsque vous déployez un service hébergé sur le cloud comme un système téléphonique dans Office 365 avec une connectivité RTC locale, vous devez garder les points suivants à l’esprit. Dans un déploiement de Skype entreprise Server 2015 Enterprise Voice de façon purement locale, l’ensemble de l’infrastructure et des clients se trouvent sur le réseau de l’entreprise. La qualité et les performances de ce réseau, qui sont essentielles pour l’audio et la vidéo de haute qualité, sont contrôlées directement par le personnel de l’entreprise. Avec le système téléphonique dans Office 365 avec une connectivité RTC locale, il existe trois réseaux concernés, dont deux sont responsables, mais un seul des membres du personnel de l’entreprise a le contrôle direct :

- **Réseau global de distribution de médias de Microsoft** L’infrastructure et le réseau mondial du Cloud de Microsoft. Office 365 et le système téléphonique dans Office 365 les serveurs et le trafic traversent ce réseau.

- **Interconnexion RTC Enterprise/Cloud** Il s’agit du réseau qui connecte votre entreprise au Cloud Office 365. Cela n’est pas nécessairement identique à votre connexion Internet générique.

- **Réseau de votre entreprise** La qualité du média en temps réel dépend fortement de votre propre réseau : en particulier le réseau WiFi et la qualité de l’interconnexion utilisée pour atteindre le nuage Office 365.

> [!NOTE]
> Pour plus d’informations sur le réglage des performances dans Skype entreprise Online, reportez-vous à la rubrique [tune Skype for Business Online performance](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US). 

## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Conditions préalables à l’utilisation du système téléphonique dans Office 365 avec une connectivité RTC locale

Avant de pouvoir configurer le système téléphonique dans Office 365 avec une connectivité RTC locale et déplacer des utilisateurs vers Skype entreprise Online, vous devez vérifier que les conditions préalables suivantes sont en place :

 **Versions de serveur local.** Les versions des serveurs de votre déploiement local doivent être indiquées dans le tableau suivant pour prendre en charge le système téléphonique dans Office 365 avec une connectivité RTC locale.


| **Rôle serveur**                                       | **Versions prises en charge\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Serveur Edge de Fédération\*\*  <br/>                            | Skype Entreprise Server 2015  <br/>                                                                              |
| Serveur de pool interne de l’itinéraire de Fédération du tronçon suivant  <br/> | Skype entreprise Server 2015, mise à jour cumulative de mars 2016 6.0.9319.235 ou ultérieure (frontal ou directeur)  <br/> |
| Serveur d’utilisateurs frontal  <br/>                          | Skype Entreprise Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Serveur Edge  <br/>                                    | Skype Entreprise Server 2015  <br/>                                                                              |
| Serveur de médiation  <br/>                               | Skype Entreprise Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*Les versions minimales prises en charge sont les suivantes :

- Skype entreprise Server 2015, mise à jour cumulative de mars 2016 6.0.9319.235

- Lync Server 2013 juillet 2015 mise à jour cumulative 5.0.8308.920

\*\*L’itinéraire de Fédération pour tous les domaines SIP pris en charge doit être acheminé via le serveur Edge Skype entreprise Server 2015 exécutant la mise à jour cumulative de mars 2016 ou supérieure. Si le pool d’utilisateurs se trouve sur Lync Server 2013, le trafic du pool externe reste sur le serveur Edge Lync Server 2013. 

En outre, vous devez vous assurer des points suivants :

- La **voix entreprise locale est configurée et testée pour les utilisateurs locaux** Cela inclut les composants de connectivité PSTN. Pour plus d’informations, reportez-vous aux rubriques suivantes si vous utilisez Skype entreprise Server 2015, reportez-vous à la rubrique [plan for Enterprise Voice in Skype for Business server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) et [Deploy Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Si vous utilisez Lync Server 2013, consultez la rubrique [planification de voix entreprise dans Lync server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) et [déploiement de voix entreprise dans Lync Server 2013](https://technet.microsoft.com/library/gg412876%28v=ocs.15%29.aspx).

- **Synchronisation Active Directory** Vous devez configurer la synchronisation Active Directory à l’aide d’Azure AD Connect. Pour plus d’informations, consultez la rubrique [Managing Azure ad Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/).

    > [!NOTE]
    > La version d’AAD Connect que vous utilisez doit être la version 1.0.9125.0 ou une version ultérieure. Si vous utilisez une version antérieure des outils AAD Connect ou de DirSync, effectuez une mise à niveau vers la version prise en charge. Vous pouvez mettre à niveau votre installation actuelle et conserver les règles personnalisées que vous avez définies dans votre environnement. 

- **Configurer votre déploiement hybride** Que tous vos utilisateurs de Skype entreprise soient actuellement hébergés en ligne ou en local, ou si vous avez actuellement une combinaison, vous devez effectuer les étapes de configuration d’un déploiement hybride de Skype entreprise Server ou de Lync Server 2013, comme indiqué dans [Deploy Hybrid Connectivity between Skype for Business Server and Office 365](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md). Pour plus d’informations générales sur les déploiements hybrides, reportez-vous à [planifier une connectivité hybride entre Skype entreprise Server et Office 365](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). 

    Si vous utilisez Lync Server 2013, reportez-vous à [Lync server 2013 hybride](https://technet.microsoft.com/library/jj204805%28v=ocs.15%29.aspx).

- **Recommandation Services ADFS (Active Directory Federation Services).** Nous vous recommandons de déployer AD FS pour prendre en charge l’authentification unique. Pour plus d’informations, consultez la rubrique [Active Directory Federation Services (AD FS)](https://technet.microsoft.com/library/cc736690%28v=ws.10%29.aspx).

Pour plus d’informations sur le déploiement du système téléphonique dans Office 365, consultez la rubrique [activation des utilisateurs pour le système téléphonique dans office 365 avec la connectivité RTC locale dans Skype entreprise Server](enable-users-for-phone-system.md).


