---
title: Planifier le système téléphonique dans Office 365 avec la connectivité PSTN locale dans Skype entreprise Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/26/2018
audience: ITPro
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
description: En savoir plus sur les considérations en matière de planification pour le système téléphonique dans Office 365 (Cloud PBX) avec la connectivité PSTN locale.
ms.openlocfilehash: 7b24c0de8eab663dea771948b066a0752fe943ca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287019"
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Planifier le système téléphonique dans Office 365 avec la connectivité PSTN locale dans Skype entreprise Server

En savoir plus sur les considérations en matière de planification pour le système téléphonique dans Office 365 (Cloud PBX) avec la connectivité PSTN locale.

Ce contenu est pertinent si vous utilisez déjà Skype entreprise Server ou Lync Server 2013 déployé en local. Pour les autres scénarios, voir [solutions de téléphonie Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions).

 Système téléphonique dans Office 365 avec la connectivité PSTN locale vous permet d’utiliser les fonctionnalités de système téléphonique (PBX Cloud) pour vos utilisateurs. Cela peut vous être utile dans les scénarios suivants :

- Certains de vos utilisateurs Skype entreprise sont hébergés sur site et d’autres dans Skype entreprise online. Vous pouvez désormais activer le système téléphonique dans les fonctionnalités d’Office 365 pour vos utilisateurs dans Skype entreprise Online, mais continuer à utiliser une connectivité PSTN locale.

- Vous disposez d’un déploiement local et vous voulez déplacer tout ou partie de vos utilisateurs vers Skype entreprise Online, mais continuer à utiliser une connectivité PSTN locale.

    > [!IMPORTANT]
    > Pour permettre aux utilisateurs de se servir d’un système téléphonique dans Office 365 avec une connectivité PSTN locale, leur adresse SIP doit être située dans votre propre domaine. L'utilisation du domaine par défaut pour Office 365, onmicrosoft.com, n'est pas prise en charge. 

Pour en savoir plus sur le système téléphonique dans Office 365, y compris les licences et les offres, voir [forfaits d’appels RTC pour Skype entreprise](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).

## <a name="feature-comparison"></a>Comparaison des fonctionnalités

Le PBX Cloud avec une connectivité PSTN locale ne propose pas la même fonctionnalité qu’une solution voix entreprise entièrement locale. Pour vous aider à déterminer si le PBX Cloud avec la connectivité PSTN locale fournit le bon jeu de fonctionnalités pour votre organisation, voir [Voici ce que vous obtenez avec PBX Cloud](https://go.microsoft.com/fwlink/?LinkId=715517).

## <a name="benefits-and-planning-considerations"></a>Avantages et points à prendre en compte en matière de planification

> [!CAUTION]
> Les appareils Lync Phone Edition DOIVENT être mis à jour vers les microprogrammes minimaux requis dans votre environnement local AVANT de passer à Skype Entreprise Online.
Si vous transférez les utilisateurs de votre déploiement local à la solution en ligne avant la mise à jour du microprogramme, les utilisateurs ne pourront pas se connecter en utilisant leur téléphone. Pour résoudre ce problème, les utilisateurs doivent être transférés à nouveau vers l’environnement local pour que leur téléphone soit mis à jour avec le microprogramme minimal requis. N’ESSAYEZ PAS DE METTRE À JOUR LE MICROPROGRAMME MINIMAL REQUIS OU D’EFFECTUER UNE MISE À JOUR MATÉRIELLE DE VOTRE TÉLÉPHONE AVANT DE REDÉPLACER L’UTILISATEUR VERS VOTRE ENVIRONNEMENT LOCAL.
Si une réinitialisation matérielle est effectuée alors que la version minimale du microprogramme n’est pas installée sur l’appareil, il utilisera par défaut l’authentification par code confidentiel, qui n’est pas prise en charge dans Skype Entreprise Online. Pour plus d’informations, reportez-vous à la rubrique [réception de téléphones pour Skype entreprise Online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).

Le déploiement du système téléphonique dans Office 365 avec la connectivité PSTN locale vous permet de déplacer vos utilisateurs vers le Cloud via Skype entreprise Online à votre rythme, tout en conservant leur connectivité PSTN locale. Si vous disposez d'un PBX, continuez à l'utiliser pour fournir une connectivité PSTN aux utilisateurs que vous transférez vers le cloud. Après le déplacement d’un utilisateur vers Skype entreprise Online et le système téléphonique dans Office 365, le téléphone PBX antérieur ne fonctionne plus, mais son numéro de téléphone est acheminé vers l’un des clients Skype entreprise pour PC ou Smartphone, ainsi que le téléphone de bureau compatible Skype entreprise. !. Une fois portée, le système téléphonique dans les utilisateurs d’Office 365 et les utilisateurs PBX traditionnels peuvent s’appeler l’un de l’autre en même temps que les appels RTC en utilisant leur numéro de téléphone normal.

Vous pouvez disposer d'une fonctionnalité personnalisée ou d'un composant supplémentaire important pour votre PBX hérité, comme un centre d'appels. Si cette fonctionnalité n’est pas disponible actuellement sur le système téléphonique dans Office 365, il est conseillé de laisser les utilisateurs qui ont besoin de cette fonctionnalité personnalisée en local avec le PBX hérité, et simplement porter les utilisateurs qui n’ont pas besoin d’accéder à la fonctionnalité personnalisée sur le système téléphonique dans Office 365 avec la connectivité PSTN locale.

Pour obtenir la liste des PBX anciens qui interagissent directement avec Skype entreprise Server 2015, voir [infrastructure Qualified pour Microsoft Lync](https://docs.microsoft.com/SkypeForBusiness/lync-cert/qualified-ip-pbx-gateway). Si votre système PBX n’est pas dans cette liste, vous pouvez utiliser un contrôleur de bordure de session pour connecter votre système PBX avec un système téléphonique dans Office 365 dans Skype entreprise online.

### <a name="network-considerations-for-quality-and-performance"></a>Considérations relatives au réseau pour la qualité et les performances

Lorsque vous déployez un service hébergé sur le cloud comme un système téléphonique dans Office 365 avec une connectivité PSTN locale, vous devez tenir compte des points suivants à l’esprit. Dans le cas d’un déploiement voix entreprise de Skype entreprise Server 2015, toutes les infrastructures et clients se trouvent sur le réseau de l’entreprise. La qualité et les performances de ce réseau, qui sont essentielles pour obtenir un son et une image de bonne qualité, sont contrôlées directement par le personnel de l'entreprise. Avec le système téléphonique dans Office 365 avec connectivité PSTN locale, il existe trois réseaux impliqués, dont deux dont le client est responsable, mais un seul d’entre eux a le contrôle direct de l’entreprise.

- **Réseau global de distribution de médias de Microsoft** Réseau et infrastructure du Cloud global de Microsoft. Office 365 et le système téléphonique dans Office 365 Servers et le trafic traverse ce réseau.

- **Interconnexion RTC entreprise/Cloud** Il s’agit du réseau qui connecte votre entreprise au Cloud Office 365. Il n'est pas forcément identique à votre connexion Internet générique.

- **Le réseau de votre entreprise** La qualité des contenus multimédias en temps réel dépend essentiellement de votre propre réseau: en particulier le réseau WiFi et la qualité de l’interconnexion utilisée pour joindre le Cloud Office 365.

> [!NOTE]
> Pour plus d’informations sur l’optimisation des performances dans Skype entreprise Online, reportez-vous à la rubrique [optimiser les performances de Skype entreprise Online](https://support.office.com/en-us/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US). 

## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Conditions préalables à l’utilisation du système téléphonique dans Office 365 avec la connectivité PSTN locale

Pour pouvoir configurer le système téléphonique dans Office 365 avec une connectivité RTC sur site et déplacer des utilisateurs vers Skype entreprise Online, vous devez vérifier que vous disposez de la configuration requise suivante:

 **Versions de serveur local.** Les versions des serveurs dans votre déploiement local doivent être répertoriées dans le tableau suivant pour prendre en charge le système téléphonique dans Office 365 avec une connectivité PSTN locale.


| **Rôle serveur**                                       | **Versions prises en charge\\**\*                                                                                         |
|:------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------|
| Bordure de Fédération\*\*  <br/>                            | Skype Entreprise Server 2015  <br/>                                                                              |
| Serveur de pool interne de l'itinéraire de fédération pour le tronçon suivant  <br/> | Skype Entreprise Server 2015, mise à jour cumulative 6.0.9319.235 de mars 2016 ou version ultérieure (Frontal ou Directeur)   <br/> |
| Serveur frontal de l'utilisateur  <br/>                          | Skype Entreprise Server 2015  <br/> Lync Server 2013  <br/>                                                      |
| serveur Edge  <br/>                                    | Skype Entreprise Server 2015  <br/>                                                                              |
| serveur de médiation  <br/>                               | Skype Entreprise Server 2015  <br/> Lync Server 2013  <br/>                                                      |

\*Les versions minimales prises en charge sont les suivantes:

- Skype Entreprise Server 2015, mise à jour cumulative 6.0.9319.235 de mars 2016

- Lync Server 2013, mise à jour cumulative 5.0.8308.920 de juillet 2015

\*\*L’itinéraire de Fédération de tous les domaines SIP pris en charge doit être acheminé via le serveur Edge Skype entreprise Server 2015 exécutant la mise à jour cumulative 2016 ou une version ultérieure. Si le pool d'utilisateurs se trouve sur Lync Server 2013, le trafic de pool externe reste sur le serveur Edge de Lync Server 2013. 

De plus, vous devez vérifier les points suivants:

- La **voix entreprise locale est configurée et testée pour les utilisateurs locaux** Cela inclut les composants de connectivité PSTN. Pour plus d’informations, reportez-vous aux rubriques suivantes si vous utilisez Skype entreprise Server 2015, reportez-vous à la rubrique [planification d’entreprise voix dans](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) Skype entreprise Server 2015 et [déploiement d’Enterprise Voice dans skype entreprise Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).

    Si vous utilisez Lync Server 2013, reportez-vous à la rubrique [planification d’Enterprise Voice dans Lync server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) et [déploiement d’Enterprise Voice dans Lync Server 2013](https://technet.microsoft.com/EN-US/library/gg412876%28v=ocs.15%29.aspx).

- **Synchronisation Active Directory** Vous devez configurer la synchronisation Active Directory à l’aide d’Azure AD Connect. Pour plus d’informations, reportez-vous à [gestion d’Azure ad Connect](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-whats-next/).

    > [!NOTE]
    > La version AAD Connect que vous utilisez doit être la version 1.0.9125.0 ou une version ultérieure. Si vous utilisez des outils d'une version antérieure d'AAD Connect ou de DirSync, effectuez une mise à niveau vers la version prise en charge. Vous pouvez mettre à niveau votre installation actuelle et conserver les règles personnalisées définies dans votre environnement. 

- **Configurer votre déploiement hybride** Que tous vos utilisateurs Skype entreprise sont actuellement hébergés en ligne ou en local, ou si vous disposez actuellement d’un mix, vous devez suivre les étapes de configuration d’un déploiement hybride de Skype entreprise Server ou Lync Server 2013, comme décrit dans la rubrique [déploiement hybride connectivité entre Skype entreprise Server et Office 365](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md). Pour plus d’informations sur les déploiements hybrides, voir [planifier une connectivité hybride entre Skype entreprise Server et Office 365](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). 

    Si vous utilisez Lync Server 2013, consultez la rubrique [hybride Lync server 2013](https://technet.microsoft.com/EN-US/library/jj204805%28v=ocs.15%29.aspx).

- **(Recommandé) services ADFS (Active Directory Federation Services** ) Nous recommandons le déploiement d’AD FS pour prendre en charge l’authentification unique. Pour plus d’informations, reportez-vous à la rubrique [AD FS (Active Directory Federation Services)](https://technet.microsoft.com/en-us/library/cc736690%28v=ws.10%29.aspx).

Pour plus d’informations sur le déploiement du système téléphonique dans Office 365, voir [activer les utilisateurs pour le système téléphonique dans office 365 avec la connectivité PSTN locale dans Skype entreprise Server](enable-users-for-phone-system.md).


