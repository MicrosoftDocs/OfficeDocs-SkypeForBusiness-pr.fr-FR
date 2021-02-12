---
title: Planifier un système téléphonique avec une connectivité PSTN en local dans Skype Entreprise Server
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
description: Découvrez les considérations de planification pour le système téléphonique (CLOUD PBX) avec une connectivité PSTN sur site.
ms.openlocfilehash: f8baab67191f32013a9d7a01ddc12f1b04b62c03
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358810"
---
# <a name="plan-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Planifier un système téléphonique avec une connectivité PSTN en local dans Skype Entreprise Server

> [!Important]
> Skype Entreprise Online sera retiré le 31 juillet 2021, après quoi le service ne sera plus accessible.  En outre, la connectivité PSTN entre votre environnement local via Skype Entreprise Server ou Cloud Connector Edition et Skype Entreprise Online ne sera plus prise en charge.  Découvrez comment connecter votre réseau téléphonique local à Teams à l’aide du [routage direct.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Découvrez les considérations de planification pour le système téléphonique (CLOUD PBX) avec une connectivité PSTN sur site.

Ce contenu est pertinent si Skype Entreprise Server ou Lync Server 2013 sont déjà déployés en local. Pour d’autres scénarios, voir [solutions de téléphonie Microsoft.](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)

 Le système téléphonique avec connectivité PSTN sur site vous permet de tirer parti des fonctionnalités du système téléphonique (PBX cloud) pour vos utilisateurs. Cela peut vous aider dans les scénarios suivants :

- Certains de vos utilisateurs Skype Entreprise sont en local et d’autres sont dans Skype Entreprise Online. Vous pouvez désormais activer les fonctionnalités et fonctionnalités du système téléphonique pour vos utilisateurs d’accueil dans Skype Entreprise Online, mais continuer à utiliser la connectivité PSTN sur site.

- Vous avez un déploiement local et vous souhaitez déplacer une partie ou la majorité de vos utilisateurs vers Skype Entreprise Online, mais continuer à utiliser la connectivité PSTN sur site.

    > [!IMPORTANT]
    > Pour activer correctement les utilisateurs pour le système téléphonique avec une connectivité PSTN sur site, leur adresse SIP doit se trouver dans votre propre domaine. L’utilisation du domaine par défaut pour Microsoft 365 ou Office 365, onmicrosoft.com, n’est pas prise en charge. 

Pour en savoir plus sur le système téléphonique, y compris les licences et les plans, consultez les [plans d’appel PSTN pour Skype Entreprise.](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)

## <a name="feature-comparison"></a>Comparaison des fonctionnalités

PbX cloud avec connectivité PSTN sur site n’offre pas le même ensemble de fonctionnalités qu’une solution Voix Entreprise sur site. Pour vous aider à déterminer si PBX Cloud avec connectivité PSTN sur site fournira l’ensemble de fonctionnalités pour votre organisation, voir Voici ce que vous obtenez avec [PBX cloud.](https://go.microsoft.com/fwlink/?LinkId=715517)

## <a name="benefits-and-planning-considerations"></a>Avantages et considérations de planification

> [!CAUTION]
> Les appareils Lync Phone Edition DOIVENT être mis à jour vers le microprogramme minimal requis dans votre environnement local AVANT de passer à Skype Entreprise Online.
Si vous déplacez vos utilisateurs de l’local vers le réseau en ligne avant de mettre à jour le microprogramme, les utilisateurs ne pourront pas se connecter à l’aide de leur téléphone. Pour résoudre ce problème, les utilisateurs doivent être déplacés vers l’environnement local pour que leurs téléphones soient mis à jour vers le microprogramme minimal. N’ESSAYEZ PAS DE METTRE À JOUR LE MICROPROGRAMME MINIMAL OU DE RÉINITIALISER MATÉRIELLEMENT LE TÉLÉPHONE AVANT DE DÉPLACER L’UTILISATEUR VERS VOTRE ENVIRONNEMENT LOCAL.
Si une réinitialisation matérielle est effectuée alors que l’appareil ne se trouve pas au microprogramme minimum, il utilise par défaut l’authentification par code confidentiel, qui n’est pas prise en charge dans Skype Entreprise Online. Pour plus d’informations, reportez-vous à [l’obtention de téléphones pour Skype Entreprise Online.](https://support.office.com/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)

En déployant le système téléphonique avec une connectivité PSTN sur site, vous pouvez déplacer vos utilisateurs vers le cloud via Skype Entreprise Online à votre rythme, tout en conservant leur connectivité PSTN sur site. Si vous avez un PBX, vous continuez à l’utiliser pour fournir une connectivité PSTN aux utilisateurs que vous déplacez vers le cloud. Une fois qu’un utilisateur est déplacé vers Skype Entreprise Online et le système téléphonique, son téléphone PBX hérité ne fonctionne plus, mais son numéro de téléphone est acheminé vers l’un des clients Skype Entreprise pour PC ou smartphones, ainsi que les téléphones de bureau compatibles Skype Entreprise. Une fois portés, les utilisateurs du système téléphonique et les utilisateurs PBX hérités peuvent s’appeler normalement et effectuer/recevoir des appels PSTN à l’aide de leur numéro de téléphone normal.

Vous disposez peut-être d’une fonctionnalité personnalisée ou d’un module plus important pour votre PBX hérité, tel qu’un centre d’appels. Si la fonctionnalité personnalisée n’est pas actuellement disponible sur le système téléphonique, vous devez laisser les utilisateurs qui ont besoin de cette fonctionnalité personnalisée localement avec le PBX hérité et simplement les mettre à disposition des utilisateurs qui n’ont pas besoin d’accéder à la fonctionnalité personnalisée vers le système téléphonique avec une connectivité PSTN locale.

Pour obtenir la liste des PBX hérités qui fonctionnent directement avec Skype Entreprise Server 2015, voir [Infrastructure qualifiée pour Microsoft Lync.](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway) Si votre PBX ne figure pas dans cette liste, vous pouvez utiliser un contrôleur de frontière de session pour connecter votre PBX au système téléphonique dans Skype Entreprise Online.

### <a name="network-considerations-for-quality-and-performance"></a>Considérations réseau pour la qualité et les performances

Lorsque vous déployez un service hébergé dans le cloud tel que le système téléphonique avec une connectivité PSTN sur site, vous devez garder les choses suivantes à l’esprit. Dans un déploiement skype entreprise server 2015 purement local Voix Entreprise, l’ensemble de l’infrastructure et des clients sont sur le propre réseau de l’entreprise. La qualité et les performances de ce réseau, qui sont essentielles pour la qualité audio et vidéo, sont sous le contrôle direct du personnel de l’entreprise. Avec le système téléphonique avec connectivité PSTN sur site, trois réseaux sont impliqués, dont deux dont le client est responsable, mais un seul dont le personnel d’entreprise a le contrôle direct :

- **Réseau de distribution de médias global de Microsoft** Le réseau et l’infrastructure cloud globaux de Microsoft. Les serveurs du système téléphonique et le trafic traversent ce réseau.

- **Connexion PSTN Entreprise/Cloud** Il s’agit du réseau qui connecte votre entreprise au cloud. Ce n’est pas nécessairement la même chose que votre connexion Internet générique.

- **Réseau de votre entreprise** La qualité du média en temps réel dépend fortement de votre propre réseau : en particulier le réseau WiFi et la qualité de l’interconnexion utilisée pour atteindre le cloud.

> [!NOTE]
> Pour plus d’informations sur l’optimisation des performances dans Skype Entreprise Online, voir [Régler les performances de Skype Entreprise Online.](https://support.office.com/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US) 

## <a name="prerequisites-for-using-phone-system-with-on-premises-pstn-connectivity"></a>Conditions préalables à l’utilisation du système téléphonique avec une connectivité PSTN sur site

Avant de configurer le système téléphonique avec une connectivité PSTN sur site et de déplacer des utilisateurs vers Skype Entreprise Online, vous devez vérifier que les conditions préalables suivantes sont en place :

 **Versions du serveur local.** Les versions des serveurs de votre déploiement local doivent être répertoriées dans le tableau suivant pour prendre en charge le système téléphonique avec une connectivité PSTN sur site.


| **Rôle serveur**                                       | **Versions prise en charge\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Edge de fédération\*\*  <br/>                            | Skype Entreprise Server 2015  <br/>                                                                              |
| Serveur de pool interne de l’itinéraire de fédération du saut suivant  <br/> | Skype Entreprise Server 2015, mise à jour cumulative 6.0.9319.235 de mars 2016 ou version supérieure (frontal ou directeur)  <br/> |
| Serveur utilisateur frontal  <br/>                          | Skype Entreprise Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| Serveur Edge  <br/>                                    | Skype Entreprise Server 2015  <br/>                                                                              |
| Serveur de médiation  <br/>                               | Skype Entreprise Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*Les versions minimales pris en charge sont :

- Skype Entreprise Server 2015, mise à jour cumulative 6.0.9319.235 de mars 2016

- Mise à jour cumulative 5.0.8308.920 de Lync Server 2013 de juillet 2015

\*\*L’itinéraire de fédération pour tous les domaines SIP pris en charge doit être acheminé via le serveur Edge Skype Entreprise Server 2015 exécutant la mise à jour cumulative de mars 2016 ou une version supérieure. Si le pool d’utilisateurs se trouve sur Lync Server 2013, ce trafic de pool externe reste sur le serveur Edge Lync Server 2013. 

En outre, vous devez vous assurer que :

- **L’Voix Entreprise local est configurée et testée pour** les utilisateurs locaux Cela inclut les composants de connectivité PSTN. Pour plus d’informations, consultez les rubriques suivantes si vous utilisez Skype Entreprise Server 2015, voir [Plan for Voix Entreprise in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) and Deploy Voix Entreprise in Skype for Business Server [2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Si vous utilisez Lync Server 2013, voir [Planning for Voix Entreprise in Lync Server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) and [Deploying Voix Entreprise in Lync Server 2013](https://technet.microsoft.com/library/gg412876%28v=ocs.15%29.aspx).

- **Synchronisation Active Directory** Vous devez configurer la synchronisation Active Directory à l’aide d’Azure AD Connect. Pour plus d’informations, voir [Gestion d’Azure AD Connect.](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/)

    > [!NOTE]
    > La version d’AAD Connect que vous utilisez doit être la version 1.0.9125.0 ou ultérieure. Si vous utilisez une version antérieure des outils AAD Connect ou DirSync, veuillez mettre à niveau vers la version prise en charge. Vous pouvez mettre à niveau votre installation actuelle et conserver les règles personnalisées que vous avez définies dans votre environnement. 

- **Configurer votre déploiement hybride** Que tous vos utilisateurs Skype Entreprise soient actuellement en ligne ou en local, ou si vous disposez actuellement d’une combinaison, vous devez effectuer les étapes de configuration d’un déploiement hybride de Skype Entreprise Server ou de Lync Server 2013, comme indiqué dans Déployer la connectivité hybride entre Skype Entreprise Server et [Office 365.](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md) Pour plus d’informations sur les déploiements hybrides, voir Planifier la connectivité hybride entre Skype Entreprise [Server et Office 365.](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) 

    Si vous utilisez Lync Server 2013, voir [Lync Server 2013 hybride.](https://technet.microsoft.com/library/jj204805%28v=ocs.15%29.aspx)

- **(Recommandé) Services AD FS (Active Directory Federation Services).** Nous vous recommandons de déployer AD FS pour prendre en charge l' sign-on unique. Pour plus d’informations, [voir Services AD FS (Active Directory Federation Services).](https://technet.microsoft.com/library/cc736690%28v=ws.10%29.aspx)

Pour plus d’informations sur le déploiement du système téléphonique, voir [Enable users for Phone System with on-premises PSTN connectivity in Skype for Business Server](enable-users-for-phone-system.md).


