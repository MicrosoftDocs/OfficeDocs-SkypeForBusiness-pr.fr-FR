---
title: Système de téléphone plan dans Office 365 avec la connectivité RTPC local dans Skype pour Business Server
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
ms.custom: Strat_SB_Hybrid
ms.assetid: 021a4c0b-d5de-4155-a506-650d758624aa
description: Obtenir des informations sur les considérations de planification pour système de téléphone dans Office 365 (Cloud PBX) avec une connectivité RTPC sur site.
ms.openlocfilehash: 5b244ea55305d88cc214875dc74837f027cc3dd5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Système de téléphone plan dans Office 365 avec la connectivité RTPC local dans Skype pour Business Server
 
Obtenir des informations sur les considérations de planification pour système de téléphone dans Office 365 (Cloud PBX) avec une connectivité RTPC sur site.
  
Ce contenu est pertinent si vous avez déjà Skype pour Business Server ou de Microsoft Lync Server 2013 déployé sur site. Pour d’autres scénarios, reportez-vous à la section [planification de votre système téléphonique dans les solutions Office 365 (Cloud PBX)](plan-your-phone-system-cloud-pbx-solution.md).
  
 Système téléphonique dans Office 365 avec la connectivité RTPC sur site vous permet d’exploiter les capacités du système de téléphone (Cloud PBX) pour vos utilisateurs. Cela peut vous être utile dans les scénarios suivants :
  
- Vous avez parmi vos Skype pour entreprise utilisateurs hébergées sur site et d’autres hôtes dans Skype pour l’activité en ligne. Vous pouvez maintenant activer le système téléphonique dans les capacités d’Office 365 et de fonctionnalités pour les utilisateurs hébergement sur Skype pour professionnels en ligne, mais continuent à utiliser la connectivité RTPC sur site.
    
- Vous disposez d’un déploiement sur site et que vous souhaitez déplacer tout ou partie de vos utilisateurs à Skype pour professionnels en ligne, mais continuer à utiliser la connectivité RTPC sur site.
    
    > [!IMPORTANT]
    > Pour correctement permettent aux utilisateurs de système téléphonique dans Office 365 avec la connectivité RTPC sur site, leur adresse SIP doit être dans votre propre domaine. L'utilisation du domaine par défaut pour Office 365, onmicrosoft.com, n’est pas prise en charge. 
  
Pour en savoir plus sur le système téléphonique dans Office 365, notamment les plans et le Gestionnaire de licences, reportez-vous à la section [plans PSTN appel Skype pour les entreprises](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
  
## <a name="feature-comparison"></a>Comparaison des fonctionnalités

PBX de nuage avec la connectivité RTPC local n’offre pas la même fonction définie comme une solution de Voix Entreprise entièrement sur site. Pour vous aider à décider si PBX de nuage avec la connectivité RTPC local fournit la fonctionnalité pour votre organisation, consultez [ici est que vous obtenez avec PBX de nuage](https://go.microsoft.com/fwlink/?LinkId=715517).
  
## <a name="benefits-and-planning-considerations"></a>Avantages et points à prendre en compte en matière de planification

> [!CAUTION]
> Les appareils Lync Phone Edition DOIVENT être mis à jour vers les microprogrammes minimaux requis dans votre environnement local AVANT de passer à Skype Entreprise Online.
Si vous transférez les utilisateurs de votre déploiement local à la solution en ligne avant la mise à jour du microprogramme, les utilisateurs ne pourront pas se connecter en utilisant leur téléphone. Pour résoudre ce problème, les utilisateurs doivent être transférés à nouveau vers l’environnement local pour que leur téléphone soit mis à jour avec le microprogramme minimal requis. N’ESSAYEZ PAS DE METTRE À JOUR LE MICROPROGRAMME MINIMAL REQUIS OU D’EFFECTUER UNE MISE À JOUR MATÉRIELLE DE VOTRE TÉLÉPHONE AVANT DE REPLACER L’UTILISATEUR DANS VOTRE ENVIRONNEMENT LOCAL.
Si la réinitialisation matérielle est effectuée avant l’installation du microprogramme minimal requis sur l’appareil, celui-ci utilise par défaut l’authentification par code confidentiel, ce qui n’est pas pris en charge par Skype Entreprise Online. Pour plus d’informations, reportez-vous à la [mise en route des téléphones pour Skype pour l’activité en ligne](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).
  
En déployant le système téléphonique dans Office 365 avec la connectivité RTPC sur site, vous pouvez déplacer les utilisateurs vers le nuage via Skype pour entreprise en ligne à votre propre rythme, tout en conservant la connectivité RTPC leurs locaux. Si vous disposez d’un PBX, vous continuez à l'utiliser pour fournir une connectivité RTC aux utilisateurs que vous transférez vers le cloud. Une fois qu’un utilisateur est déplacé à Skype pour Business Online et système téléphonique dans Office 365, leur téléphone PBX hérité ne fonctionnera plus, mais que son numéro de téléphone route vers de la Skype pour les clients de l’entreprise pour PC ou des téléphones intelligents ainsi que Skype pour téléphone de bureau compatible à l’entreprise s. Une fois les ports, système téléphonique dans Office 365 utilisateurs et utilisateurs de PBX hérités peuvent normalement s’appellent mutuellement ainsi que marque/recevoir les appels RTPC à l’aide de son numéro de téléphone normal.
  
Vous pouvez disposer d'une fonctionnalité personnalisée ou d'un composant supplémentaire important pour votre PBX hérité, comme un centre d'appels. Si la fonctionnalité personnalisée n’est pas actuellement disponible sur le système téléphonique dans Office 365, vous devez laisser aux utilisateurs qui requièrent cette fonctionnalité personnalisée sur site avec le PBX hérité et port seulement les utilisateurs qui n’ont pas besoin d’accéder à la fonctionnalité personnalisée au système téléphonique dans Office 365 avec la connectivité RTPC sur site.
  
Pour obtenir une liste de PBX hérité qui interagissent directement avec Skype pour Business Server 2015 voir [Infrastructure qualifié pour Microsoft Lync](https://technet.microsoft.com/en-us/office/dn788945.aspx). Si votre système PBX ne se trouve pas sur cette liste, vous pouvez utiliser un contrôleur de bordure de Session pour connecter votre PBX avec système de téléphone dans Office 365 dans Skype pour l’activité en ligne.
  
### <a name="network-considerations-for-quality-and-performance"></a>Considérations relatives au réseau pour la qualité et les performances

Lors du déploiement d’un service hébergé sur le nuage comme système téléphonique dans Office 365 avec la connectivité RTPC sur site, vous devez conserver les éléments suivants à l’esprit. Dans un Skype purement sur site pour le déploiement de Voix Entreprise de Business Server 2015, l’infrastructure et les clients sont sur le réseau de l’entreprise. La qualité et les performances de ce réseau, qui sont essentielles pour obtenir un son et une image de bonne qualité, sont contrôlées directement par le personnel de l’entreprise. Système de téléphone dans Office 365 avec la connectivité RTPC sur site, il existe trois réseaux concernés, dont le client est responsable des deux mais seul dont le personnel de l’entreprise a un contrôle direct :
  
- **Réseau de diffusion Global Support de Microsoft** Infrastructure et réseau de nuage global de Microsoft. Office 365 et système téléphonique dans le trafic et les serveurs Office 365 parcourent ce réseau.
    
- **Interconnexion d’entreprise/nuage RTPC** Ceci est le réseau qui connecte votre entreprise vers le nuage d’Office 365. Il n'est pas forcément identique à votre connexion Internet générique.
    
- **Votre réseau d’entreprise** La qualité du support en temps réel dépend fortement de votre propre réseau : en particulier le réseau Wi-Fi et la qualité de l’interconnexion utilisée pour atteindre le nuage d’Office 365.
    
> [!NOTE]
> Pour plus d’informations sur le réglage des performances dans Skype pour professionnels en ligne, voir [Régler la Skype pour les performances commerciales en ligne](https://support.office.com/en-us/article/Tune-Skype-for-Business-Online-performance-beec23c2-c5d6-4e84-a8af-e82aefca7802?ui=en-US&amp;rs=en-US&amp;ad=US). 
  
## <a name="prerequisites-for-using-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Composants requis pour utiliser le système téléphonique dans Office 365 avec la connectivité RTPC sur site

Avant de pouvoir configurer système téléphonique dans Office 365 avec connectivité RTPC de locaux et de déplacer les utilisateurs Skype pour professionnels en ligne, vous devez confirmer que vous disposez les conditions préalables suivantes :
  
 **Versions serveur local.** Les versions de serveurs dans votre déploiement sur site doivent figurer dans le tableau suivant pour prendre en charge un système téléphonique dans Office 365 avec la connectivité RTPC sur site.
  
|**Rôle de serveur**|**Versions prises en charge\***|
|:-----|:-----|
|Bord de fédération\*\*  <br/> |Skype Entreprise Server 2015  <br/> |
|Serveur de pool interne de l'itinéraire de fédération pour le tronçon suivant  <br/> |Skype Entreprise Server 2015, mise à jour cumulative 6.0.9319.235 de mars 2016 ou version ultérieure (Frontal ou Directeur)  <br/> |
|Serveur frontal de l'utilisateur  <br/> |Skype Entreprise Server 2015  <br/> Lync Server 2013  <br/> |
|Serveur Edge  <br/> |Skype Entreprise Server 2015  <br/> |
|Serveur de médiation  <br/> |Skype Entreprise Server 2015  <br/> Lync Server 2013  <br/> |
   
\*Les versions minimales de prise en charge sont les suivants :
  
- Skype Entreprise Server 2015, mise à jour cumulative 6.0.9319.235 de mars 2016
    
- Lync Server 2013, mise à jour cumulative 5.0.8308.920 de juillet 2015
    
\*\*La fédération de routage pour tous les domaines SIP pris en charge doivent repositionner le Skype pour l’exécution du serveur de transport Edge Business Server 2015 mise à jour Cumulative des mars 2016 ou une version ultérieure. Si le pool d'utilisateurs se trouve sur Lync Server 2013, le trafic de pool externe reste sur le serveur Edge de Lync Server 2013. 
  
En outre, vous devez vérifier les éléments suivants :
  
- **De Voix Entreprise sur site est configuré et testé pour les utilisateurs locaux** Cela inclut les composants de connectivité RTPC. Pour plus d’informations, consultez les rubriques suivantes si vous utilisez Skype pour Business Server 2015, voir [planification de Voix Entreprise dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) et [Déploiement de Voix Entreprise dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md).
    
    Si vous utilisez Lync Server 2013, voir [planification de Voix Entreprise dans Lync Server 2013](https://technet.microsoft.com/library/gg413081%28v=ocs.15%29.aspx) et [Déploiement de Voix Entreprise dans Lync Server 2013](https://technet.microsoft.com/EN-US/library/gg412876%28v=ocs.15%29.aspx).
    
- **Synchronisation de Active Directory** Vous devez configurer la synchronisation de Active Directory à l’aide d’Azure Connect d’Active Directory. Pour plus d’informations, voir [gestion de Azure AD Connect](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-whats-next/).
    
    > [!NOTE]
    > La version AAD Connect que vous utilisez doit être la version 1.0.9125.0 ou une version ultérieure. Si vous utilisez des outils d'une version antérieure d'AAD Connect ou de DirSync, effectuez une mise à niveau vers la version prise en charge. Vous pouvez mettre à niveau votre installation actuelle et conserver les règles personnalisées définies dans votre environnement. 
  
- **Configurer votre déploiement hybride** Si tous vos Skype pour les utilisateurs professionnels sont actuellement hébergement soit en ligne ou sur site, ou si vous avez actuellement un mélange, vous devez effectuer les étapes pour configurer un déploiement hybride de Skype pour Business Server ou de Lync Server 2013, comme indiqué dans [Déploiement hybride connectivité entre Skype pour Business Server et Skype pour Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md). Pour plus d’informations sur les déploiements hybride, voir [planification de la connectivité d’hybride entre Skype pour Business Server et Skype pour l’activité en ligne](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md). 
    
    Si vous utilisez Lync Server 2013, consultez [hybride de Lync Server 2013](https://technet.microsoft.com/EN-US/library/jj204805%28v=ocs.15%29.aspx).
    
- **(Recommandé) Active Directory Federation Services (ADFS)** Nous vous recommandons de déployer AD FS pour prendre en charge l’ouverture de session unique. Pour plus d’informations, consultez [Services de fédération Active Directory (Active Directory Federation Services)](https://technet.microsoft.com/en-us/library/cc736690%28v=ws.10%29.aspx).
    
Pour plus d’informations sur le déploiement du système téléphonique dans Office 365, reportez-vous à la section [Activer les utilisateurs pour le système téléphonique dans Office 365 avec la connectivité RTPC dans Skype pour Business Server local](enable-users-for-phone-system.md).
  

