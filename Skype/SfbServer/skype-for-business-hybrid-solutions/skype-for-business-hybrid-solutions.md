---
title: Skype pour des solutions professionnelles hybride
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0b038686-ed36-4867-9653-14cc08c919cb
description: Trouvez des informations sur la planification d’un Skype pour un déploiement hybride Business.
ms.openlocfilehash: 124286ea60b1bd032d9d736284a738c63aea2dc6
ms.sourcegitcommit: 8a34b5f0295fc6059852dab6971429fda4d30b67
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2018
ms.locfileid: "20176190"
---
# <a name="skype-for-business-hybrid-solutions"></a>Skype pour des solutions professionnelles hybride
 
Trouvez des informations sur la planification d’un Skype pour un déploiement hybride Business. 
  
Cette rubrique vous présente plusieurs configurations hybrides afin de vous aider à déterminer celle qui est la plus adaptée à votre entreprise. Vous pourrez ensuite en savoir plus sur la configuration qui vous intéresse en suivant les liens correspondants. Cette rubrique contient les sections suivantes :
  
- [Configurations hybrides Skype Entreprise](skype-for-business-hybrid-solutions.md#BKMK_HybridConfigurations)
    
- [Ajoutez Skype pour Business Online sur vos locaux Skype pour un environnement d’entreprise](skype-for-business-hybrid-solutions.md#BKMK_HybridConnectivity)
    
- [Tirer parti de système téléphonique dans Office 365 (en nuage PBX)](skype-for-business-hybrid-solutions.md#BKMK_CloudPBX)
    
- [Intégration dans Exchange et SharePoint](skype-for-business-hybrid-solutions.md#BKMK_IntegratewExchangeSharePoint)
    
- [Planifier et configurer un environnement hybride](skype-for-business-hybrid-solutions.md#BKMK_Tasks)
    
- [Pour plus d’informations](skype-for-business-hybrid-solutions.md#BKMK_MoreInfo)
    
## <a name="skype-for-business-hybrid-configurations"></a>Configurations hybrides Skype Entreprise
<a name="BKMK_HybridConfigurations"> </a>

Skype pour les entreprises prend en charge plusieurs configurations hybrides. Vous pouvez ajouter Skype pour Business Online sur vos locale Skype pour un environnement d’entreprise, intégrer votre Skype pour le déploiement d’entreprise avec Exchange Online et SharePoint Online et tirer parti de système téléphonique dans Office 365 (en nuage PBX) — de Microsoft technologie d’activation du contrôle d’appel et les fonctionnalités d’autocommutateur privé (PBX) dans le nuage Office 365 avec Skype pour Business en ligne. 
  
Avec un Skype pour un déploiement hybride Business, vous combinez un Skype pour l’abonnement en ligne professionnels avec votre Skype locale offre d’entreprise. Vous pouvez commencer à créer des compétences de gestion du logiciel en tant que service dans votre organisation et déplacez votre Skype pour les utilisateurs vers le nuage à votre rythme. Les utilisateurs qui sont hébergés dans le nuage peuvent tirer parti du système téléphonique dans Office 365 tout en conservant votre connectivity de Public réseau de téléphonique commuté (RTC) sur site.
  
Avec un Skype pour la configuration hybride Business, gardez les points suivants à l’esprit :
  
- Certains utilisateurs seront peut-être hébergés en local et certains le seront en ligne, mais ils partageront le même domaine de protocole SIP, comme par exemple contoso.com.
    
- Vous pouvez migrer les utilisateurs de Skype pour les entreprises dans les locaux à Skype pour Business Online au fil du temps, votre calendrier.
    
- L’intégration dans d’autres applications Microsoft Office 365, y compris Exchange Online et SharePoint Online est possible.
    
- L’intégration dans Exchange et SharePoint est possible.
    
- Vous pouvez profiter de la fonction Diffusion de réunion Skype.
    
- Vous pouvez profiter de la fonction conférence RTC.
    
## <a name="add-skype-for-business-online-into-your-existing-on-premises-skype-for-business-environment"></a>Ajoutez Skype pour Business Online sur vos locaux Skype pour un environnement d’entreprise
<a name="BKMK_HybridConnectivity"> </a>

Connectivité hybride entre Skype pour Business Server et Skype pour Business Online signifie que les utilisateurs d’un domaine, par exemple, contoso.com, sont répartis entre l’utilisation de Skype pour Business Server localement et Skype pour Business Online. Certains utilisateurs du domaine sont hébergés en local et certains le sont en ligne. Vous pouvez configurer votre déploiement sur site pour l’environnement hybride avec Skype pour Business Online et utiliser la synchronisation Active Directory pour conserver votre organisation locale et en ligne utilisateurs synchronisés. 
  
Le diagramme suivant montre comment ajouter des Skype pour Business Online dans votre Skype local existant pour l’environnement d’entreprise, ce qui vous permet de déplacer des utilisateurs vers le nuage à votre rythme :
  
![Configuration hybride de Skype Entreprise](../media/4580f2c8-7008-4c6e-826c-020d0f2d1636.png)
  
Pour plus d’informations, voir [planification de la connectivité hybride entre Skype pour Business Server et Skype pour Business Online](plan-hybrid-connectivity.md) et de [déployer la connectivité hybride entre Skype pour Business Server et Skype pour Business Online](deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="take-advantage-of-phone-system-in-office-365-cloud-pbx"></a>Tirer parti de système téléphonique dans Office 365 (en nuage PBX)
<a name="BKMK_CloudPBX"> </a>

 Système téléphonique dans Office 365 (en nuage PBX) est la technologie de Microsoft pour activer le contrôle d’appel et les fonctionnalités d’autocommutateur privé (PBX) dans le nuage Office 365 avec Skype pour Business en ligne. Système téléphonique dans Office 365 vous permet de remplacer votre système PBX existant par un ensemble de fonctionnalités provenant d’Office 365 et étroitement intégré à l’expérience de productivité de Microsoft dans le nuage.
  
En plus de deux système téléphonique dans les offres Office 365 hybride, Microsoft offre un système téléphonique dans Office 365 avec l’appel planifier — un PSTN appel service — pour une solution tout-en nuage qui ne nécessite pas un déploiement du serveur local. Pour décider si système téléphonique dans Office 365 avec l’appel de planification peut être la solution idéale pour votre organisation, consultez la rubrique [Système téléphonique dans les solutions Office 365](plan-your-phone-system-cloud-pbx-solution/plan-your-phone-system-cloud-pbx-solution.md#BKMK_PBXOfferings).
  
Il existe deux système téléphonique dans les offres Office 365 hybride : 
  
- [Système téléphonique dans Office 365 avec une connectivité locale fournie par votre Skype pour le déploiement de serveur d’entreprise](skype-for-business-hybrid-solutions.md#BKMK_Server)
    
- [Système téléphonique dans Office 365 avec une connectivité locale fournie par Skype pour Business Server nuage connecteur Edition](skype-for-business-hybrid-solutions.md#BKMK_CCE)
    
### <a name="phone-system-in-office-365-with-on-premises-connectivity-provided-by-your-skype-for-business-server-deployment"></a>Système téléphonique dans Office 365 avec une connectivité locale fournie par votre Skype pour le déploiement de serveur d’entreprise
<a name="BKMK_Server"> </a>

Cette configuration comprend un Skype pour déploiement local de Business Server modifiée pour un environnement hybride PSTN. Les utilisateurs de votre organisation qui sont hébergés dans le nuage peuvent recevoir les services de PBX à partir du cloud Microsoft, mais une connectivité PSTN fournie par Enterprise Voice sur votre Skype sur site pour le déploiement de serveur d’entreprise. 
  
![PBX Cloud avec déploiement Skype Entreprise Server](../media/d4136bbc-b01e-469c-bf94-90ba59c61cda.png)
  
Cette configuration est la meilleure si : 
  
- Votre système PBX n’offre pas de fonctionnalités uniques que vous devez conserver.
    
- Plan, le service Office 365 PSTN d’appel, l’appel n’est pas disponible dans votre région.
    
- Vous avez un Lync existant ou un Skype pour le déploiement de serveur d’entreprise.
    
Pour plus d’informations, voir [planifier le système téléphonique dans Office 365 avec une connectivité PSTN dans Skype pour Business Server sur site](plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md) et [activer des utilisateurs pour le système téléphonique dans Office 365 avec une connectivité PSTN dans Skype pour Business Server local](plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system.md).
  
### <a name="phone-system-in-office-365-with-on-premises-connectivity-provided-by-skype-for-business-server-cloud-connector-edition"></a>Système téléphonique dans Office 365 avec une connectivité locale fournie par Skype pour Business Server nuage connecteur Edition
<a name="BKMK_CCE"> </a>

Cette configuration consiste en un ensemble de machine virtuelles (VM) qui mettent en œuvre la connectivité RTC locale. En déployant un Skype minimal pour la topologie Business Server dans un environnement virtualisé, les utilisateurs de votre organisation qui sont hébergés dans le nuage peuvent recevoir les services de PBX à partir du cloud Microsoft, mais une connectivité PSTN est fournie par le biais de la voix sur site existant infrastructure. 
  
![CloudPBXCloudConnectorEdition](../media/7a6ee221-bfe1-422b-ac44-6446db6b766c.png)
  
Cette configuration est la meilleure si :
  
- Votre système PBX n’offre pas de fonctionnalités uniques que vous devez conserver.
    
- Plan, le service Office 365 PSTN d’appel, l’appel n’est pas disponible dans votre région.
    
- Ne pas un Lync existant ou Skype pour le déploiement de serveur d’entreprise.
    
Pour plus d’informations, voir [planifier Skype pour l’édition de connecteur Business Cloud](plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="integrate-with-exchange-and-sharepoint"></a>Intégration dans Exchange et SharePoint
<a name="BKMK_IntegratewExchangeSharePoint"> </a>

Un Skype pour la configuration hybride Business vous permet d’intégrer avec d’autres applications Microsoft Office 365, notamment Exchange Online et SharePoint Online.
  
### <a name="skype-for-business-server-with-exchange-online-and-sharepoint-online"></a>Skype Entreprise Server dans Exchange Online et SharePoint Online

Vous pouvez intégrer Skype pour Business Server avec Exchange Online et SharePoint Online, comme illustré dans le diagramme suivant :
  
![Skype Entreprise Server dans Exchange Online et SharePoint Online](../media/9f456ed2-8777-4a20-a519-c87dfc56b7f5.png)
  
Intégration Skype pour Business Server avec Exchange Online et SharePoint Online présente plusieurs avantages. Vous pouvez :
  
- Utilisez l’ensemble complet des fonctionnalités de Skype pour Business Server.
    
- Exploiter votre équipement téléphonique local existant, tel que PBX.
    
- Utiliser Exchange Online pour vos e-mail, ce qui allège la charge de traitement et de stockage des serveurs locaux.
    
- Utiliser SharePoint Online pour collaborer, ce qui allège la charge de maintenance des serveurs SharePoint locaux.
    
- Utiliser Skype pour entreprises, Exchange et SharePoint intégré des fonctionnalités, y compris la messagerie unifiée dans Office 365.
    
Pour plus d’informations, voir [planifier l’intégration Skype pour les entreprises et Exchange](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  
### <a name="exchange-server-with-skype-for-business-online"></a>Exchange Server avec Skype Entreprise Online

Vous pouvez intégrer Exchange Server Skype pour Business Online comme indiqué dans le diagramme suivant :
  
![Intégration d’Exchange à Skype Entreprise Online](../media/e8ca44ad-f47c-46a3-9cef-8fe7deafd615.png)
  
Intégration d’Exchange Server avec Skype pour Business Online offre les avantages suivants :
  
- Exploitation de votre infrastructure Exchange existante.
    
- Utiliser Skype pour Business Online pour les fonctionnalités de présence, messagerie instantanée et la conférence. 
    
Pour plus d’informations, voir [planifier l’intégration Skype pour les entreprises et Exchange](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  
## <a name="tasks-for-planning-and-configuring-a-hybrid-environment"></a>Planifier et configurer un environnement hybride
<a name="BKMK_Tasks"> </a>

Skype pour les entreprises fournit un large éventail de fonctionnalités, quel que soit le mode de l’architecture de votre déploiement. L’architecture que vous choisirez déterminera les responsabilités IT dont vous aurez la charge, et celles dont Microsoft s’occupera dans le cadre de votre abonnement. Quelle que soit la meilleure architecture pour votre organisation, vous aurez toujours la charge de ces cinq responsabilités fondamentales :
  
- **Mise en réseau et connectivité** - assurer la disponibilité via le pare-feu, les serveurs proxy, les passerelles et sur les liaisons WAN et la capacité du réseau en effectuant une évaluation du réseau ou en contractantes avec un partenaire pour effectuer l’évaluation.
    
- **La gouvernance des données &amp; gestion des droits** - classer vos données sensibles et vérifiez qu’il est protégé et surveillé partout où il est stocké et s’il est en transit.
    
- **Points de terminaison clients** - établir, mesurer et appliquer des normes de sécurité modernes sur les périphériques qui sont utilisés pour accéder à vos données et les ressources.
    
- **Compte &amp; accéder à la gestion** - établir un profil pour des activités de compte « normal » et d’alerte sur l’activité inhabituelle.
    
- **Identité** : Utilisez des informations d’identification sécurisées par le matériel ou par Multi-Factor Authentication (MFA) pour toutes les identités. 
    
En plus des tâches liées à l’architecture que vous effectuez pour votre environnement local, vous aurez à :
  
- Planifier et concevoir les exigences de gestion d’identité, y compris l’intégration des identités locales dans Office 365.
    
- Vous assurer de la capacité et de la disponibilité du réseau.
    
- Acquérir des certificats SSL tiers, afin de fournir une sécurité d’entreprise pour les offres de services Office 365.
    
- Décider si vous voulez vous connecter à Office 365 par l’intermédiaire du protocole IPv6.
    
- Déterminer quelle fonctionnalité d’intégration avec locaux et des versions en ligne de Skype pour entreprises, Exchange et SharePoint est souhaitée. 
    
- Déterminer quel serveur proxy sera utilisé pour les requêtes d’Office 365.
    
Vous devez également effectuer le suivi des tâches professionnels de l’informatique pour implémenter votre Skype pour un environnement hybride :
  
- Vérifiez que vous disposez d’un client Microsoft Office 365 avec Skype pour Business Online activé.
    
- Mettre en œuvre le plan de gestion d’identité.  
    
- Planifier et exécuter le routage et l’enregistrement DNS interne et externe.
    
- Configurer votre pare-feu ou votre proxy pour les exigences d’URL et d’adresse IP d’Office 365.
    
- Administrer des comptes d’utilisateurs et Skype pour les paramètres d’entreprise en ligne. 
    
- Configurer le serveur proxy, si besoin.  
    
- Configurer l’intégration des fonctionnalités dans les versions locales et en ligne d’Exchange Server et de SharePoint.
    
## <a name="for-more-information"></a>Pour plus d’informations
<a name="BKMK_MoreInfo"> </a>

Pour plus d’informations, consultez les ressources suivantes :
  
- [Ressources d’architecture informatique en nuage Microsoft](https://aka.ms/clouditarch)
    
- [Identité du cloud Microsoft pour les architectes de l’entreprise](https://docs.microsoft.com/en-us/office365/enterprise/microsoft-cloud-it-architecture-resources#identity)
    
- [Préparer votre organisation à Office 365 pour entreprises](https://aka.ms/O365EntPrep)
    
- [Planifier une connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online](plan-hybrid-connectivity.md)
    
- [Déploiement de la connectivité hybride entre Skype Entreprise Server et Skype Entreprise Online](deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)
    
- [Système téléphonique dans les solutions Office 365](plan-your-phone-system-cloud-pbx-solution/plan-your-phone-system-cloud-pbx-solution.md#BKMK_PBXOfferings)
    
- [Planifier l’intégration de Skype Entreprise et d’Exchange](../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
    
Si vous souhaitez télécharger cette rubrique dans un format d’affiche, rendez-vous sur :
  
- [Skype pour l’architecture des modèles d’entreprise (pdf)](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)
    
- [Skype pour des modèles d’entreprise architecturaux (Visio)](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)
    

