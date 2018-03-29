---
title: Planification pour Skype Entreprise, version Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
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
ms.assetid: 6ce0e580-8c4a-45de-a54f-e39e438335d6
description: Obtenez des informations sur la version Cloud Connector de Skype Entreprise, un ensemble de machines virtuelles (VM) qui met en œuvre une connectivité PSTN locale avec un système téléphonique d'Office 365 (Cloud PBX).
ms.openlocfilehash: f69becbd25ad00ca4353c0b287f2abcc43bdecfd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Planification pour Skype Entreprise, version Cloud Connector
 
Obtenez des informations sur la version Cloud Connector de Skype Entreprise, un ensemble de machines virtuelles (VM) qui met en œuvre une connectivité PSTN locale avec un système téléphonique d'Office 365 (Cloud PBX). 
  
Édition de connecteur de nuage peut être la solution idéale pour votre organisation si vous ne disposez pas un existant de Lync Server ou les Skype pour le déploiement du serveur de l’entreprise. Si vous êtes à l’étude chez lequel dans les solutions Office 365 est adaptée à votre entreprise, reportez-vous à la section [planification de votre système téléphonique dans les solutions Office 365 (Cloud PBX)](plan-your-phone-system-cloud-pbx-solution.md). 
  
Ce document décrit les exigences en matière d’édition de connecteur de nuage et les topologies prises en charge et vous aide à planifier le déploiement de l’édition de connecteur de nuage. Assurez-vous de lire cette rubrique avant de configurer votre environnement de connecteur de nuage. Lorsque vous êtes prêt à déployer et configurer l’édition de connecteur de nuage, consultez [configurer et de gérer des Skype pour connecteur de Cloud Business Edition](configure-skype-for-business-cloud-connector-edition.md). 
  
Connecteur de nuage version 2.1 est à présent disponible. Si vous n’êtes pas encore passé à 2.1, consultez [mise à niveau vers une nouvelle version de connecteur de nuage](upgrade-to-a-new-version-of-cloud-connector.md). Vous pouvez trouver le fichier d’installation à [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller). 
  
> [!NOTE]
> Microsoft prend en charge la version précédente du nuage lien édition pendant 60 jours après la publication d’une nouvelle version. Microsoft prend en charge la version 2.0.1 pendant 60 jours après la sortie de la version 2.1 pour vous laisser le temps de la mettre à niveau. Toutes les versions antérieures à 2.0.1 ne sont plus prises en charge. 
  
Edition de connecteur de cloud est un hybride offre qui se compose d’un ensemble de paquets Machines virtuelles (VM) qui implémentent la connectivité RTPC local avec système de téléphone dans Office 365. En déployant un minimum Skype pour la topologie du serveur de l’entreprise dans un environnement virtualisé, les utilisateurs de votre organisation qui sont hébergées dans le cloud peuvent recevoir des services PBX du nuage de Microsoft, mais la connectivité RTPC est fournie par le biais de la voix sur site existant infrastructure. 
  
![Diagramme de topologie montrant Cloud PBX Gateway reliant Cloud PBX à un déploiement local de Skype Entreprise.](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)
  
Comme Cloud Connector vous permert d'intégrer le système téléphonique dans les services d'Office 365 à votre environnement téléphonique actuel (par exemple PBX, des appareils analogiques et des centres d'appels), vous pouvez implémenter une migration progressive vers le système téléphonique d'Office 365. 
  
Par exemple, imaginons que votre entreprise possède un centre d'appels sophistiqué avec des fonctionnalités spécifiques que le système téléphonique d'Office 365 ne fournit pas. Vous pouvez choisir de garder la solution existante pour les utilisateurs du centre d'appels, mais de déplacer les autres utilisateurs vers le système téléphonique d'Office 365. 
  
Cloud Connector se chargera du routage entre les utilisateurs hébergés localement et ceux hébergés en ligne, et vous pouvez choisir d'utiliser votre propre fournisseur PSTN avec le système téléphonique d'Office 365.
  
Lors de la planification de votre déploiement de Cloud connecteur Edition, prenez en compte les éléments suivants : 
  
- Pour utiliser le connecteur du nuage pour tirer parti des solutions de nuage voix, vous devrez vous inscrire pour un client Office 365 qui comprend un système téléphonique dans Office 365. Si vous n’avez pas encore un client Office 365, vous découvrirez comment Inscrivez-vous ici : [Office 365 pour entreprises](https://products.office.com/en-us/business/office). Notez que vous devez souscrire à un plan qui inclut Skype pour l’activité en ligne.
    
- Pour inscrire des appliances de connecteur de Cloud avec le Skype pour service d’entreprise en ligne et à l’exécution de diverses applets de commande, connecteur nuage 2.0 et versions ultérieur nécessite un compte Office 365 dédié avec le Skype pour les droits de l’administrateur de clients d’entreprise. Les versions de Cloud Connector antérieures à 2.0 requièrent un compte Office 365 dédié disposant des droits d'administrateur client global.
    
- Connecteur de nuage ne nécessite pas une complète sur site Skype pour le déploiement du serveur de l’entreprise. 
    
    Actuellement, connecteur de nuage ne peut pas coexister avec Lync ou Skype pour entreprise serveurs sur site. Si vous souhaitez déplacer Lync existant ou Skype pour les utilisateurs professionnels vers Office 365 et conserver fournissant sur site téléphonique à vos utilisateurs, pensez à système téléphonique dans Office 365 avec connectivité sur site à l’aide d’un Skype existant pour le déploiement du serveur de l’entreprise. Pour plus d’informations, reportez-vous à la section [planification de votre système téléphonique dans les solutions Office 365 (Cloud PBX)](plan-your-phone-system-cloud-pbx-solution.md) et de [Planifier le système téléphonique dans Office 365 avec la connectivité RTPC local dans Skype pour Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Si vous aviez un Skype précédent pour le déploiement d’entreprise ou de Lync Server et que vous avez étendu le schéma, il est inutile de nettoyer le schéma pour le déploiement de connecteur de nuage, tant que vous avez retirées Skype tous les composants métier ou Lync Server de votre environnement. 
    
- Vos utilisateurs sont hébergés en ligne.
    
- Si votre organisation a configuré la synchronisation Active Directory (DirSync), tous les comptes des utilisateurs planifiés pour la voix hybride doivent être créés en premier lieu localement, puis synchronisés vers le cloud.
    
- Vous pouvez conserver votre opérateur RTC actuel, si nécessaire.
    
- Si vous souhaitez fournir des conférences à distance aux utilisateurs hébergés sur le connecteur de nuage, vous pouvez acheter les conférence PSTN de Microsoft ou de partenaires de fournisseur (ACP) audioconférence.
    
- Cloud Connector 2.0 et les version ultérieures prennent désormais en charge la déviation du trafic. Le contournement de média permet au client d’envoyer le CD directement sur le tronçon suivant de commutation de téléphone RTPC (réseau Public), une passerelle ou un contrôleur de Session en périphérie (SBC) — et d’éliminer le composant d’édition de connecteur de nuage du chemin d’accès de média. Pour plus d’informations, reportez-vous à [planification des médias ignorer dans le nuage lien édition](plan-for-media-bypass-in-cloud-connector-edition.md).
    
- Cloud Connector 2.1 et les versions ultérieures prennent en charge la surveillance de Cloud Connector avec Operations Management Suite (OMS). Pour plus d’informations, voir [Analyseur de connecteur de Cloud à l’aide de la Suite de gestion des opérations (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)
    
- Connecteur de nuage n’est disponible dans tous les pays où E5 d’entreprise Office 365 est disponible. Toutefois, en raison de réglementations diverses, nuage connecteur ne peut pas être configuré si l’emplacement du client est défini à l’un des pays suivants : Algérie, Bangladesh, Botswana, Brunei, Cameroun, côte d’Ivoire, Ghana, Liban, Macao, Maurice, Namibie, le Paraguay, Sénégal.
    
Cette rubrique contient les sections suivantes :
  
- [Composants d’édition de connecteur de nuage](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)
    
- [Topologies d’édition du connecteur de nuage](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)
    
- [Configuration requise pour le déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)
    
- [Informations à recueillir avant le déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)
    
- [Aspects relatifs au plan de numérotation](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)
    
- [Considérations relatives à la haute disponibilité](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)
    
- [Trafic multimédia de Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)
    
- [Surveillance et dépannage](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)
    
- [Pour plus d'informations](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)
    
## <a name="cloud-connector-edition-components"></a>Composants de la version Cloud Connector
<a name="BKMK_Components"> </a>

Avec l’édition du connecteur de nuage, vous déployez un ensemble de machines virtuelles emballés contenant un Skype minimal pour la topologie du serveur de l’entreprise, consistant en un composant de bord, composant de médiation et un rôle du magasin Central de gestion (MCG). Vous allez également installer un contrôleur de domaine, qui est requis pour le fonctionnement interne du connecteur de nuage. Ces services sont configurés pour hybride avec vos clients Office 365 incluant Skype pour les services professionnels en ligne.
  
![Composants de la version Cloud Connector](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)
  
Composants du connecteur nuage fournissent les fonctionnalités suivantes :
  
- **Composant de bord** - Communication entre la topologie de site et les services en ligne passe par le composant de bord, qui inclut les composants suivants :
    
  - **Access Edge** - en fournit un routage entre le déploiement sur site et Skype pour Business Online de SIP.
    
  - **Le relais multimédia** - permet le routage de support entre le composant de médiation et d’autres points de terminaison multimédia.
    
  - **L’authentification relais de média / MRAS** -génère des jetons d’accès pour le relais multimédia.
    
- **Routage sortant** - fournit l’équilibrage du trafic voix entre les passerelles de charge ou SBCs reliés à un matériel de connecteur de nuage. Les appels seront répartis équitablement entre tous les SBC et passerelles connectés à l'appliance Cloud Connector.
    
    Permet le routage pour les passerelles basées sur des règles. Uniquement les stratégies globales qui sont basés sur des numéros RTPC (sortants) de destination sont pris en charge.
    
- **Rôle de stocker de gestion centrale (CMS)** - inclut le magasin de configuration pour les composants de la topologie, y compris le transfert de fichiers CMS.
    
- **Réplica du magasin central de gestion (MCG)** - synchronise les informations de configuration à partir de la base de données CMS globale sur le serveur de rôle CMS.
    
- **Contrôleur de domaine** - nuage connecteur Active Directory Domain Services pour stocker tous les paramètres globaux et les groupes nécessaires pour déployer les composants du connecteur du nuage. Une forêt sera créée pour chaque solution matérielle-logicielle connecteur de nuage. Le contrôleur de domaine ne doit pas avoir toutes les connexions avec Active Directory de la production. Les services Active Directory comprennent :
    
  - Services de domaine Active Directory
    
  - Services de certificats Active Directory permettant d'émettre des certificats internes
    
- **Composant de médiation** - protocole de mappage de passerelle implémente SIP et les médias entre Skype pour les passerelles Business et RTPC. Comprend un réplica de MCG qui synchronise la configuration à partir de la base de données CMS global.
    
## <a name="cloud-connector-edition-topologies"></a>Topologies de la version Cloud Connector
<a name="BKMK_Topologies"> </a>

Dans le cadre de cet article, nous les appellerons « sites RTC ». Un site RTC est une combinaison de matériel de connecteur de nuage, déployé au même emplacement et avec les passerelles RTPC communs connectés. Les sites RTC permettent d’effectuer les opérations suivantes :
  
- Fournir une connectivité aux passerelles les plus proches de vos utilisateurs.
    
- Permettre une évolutivité en déployant plusieurs appliances de connecteur du Cloud dans un ou plusieurs sites RTPC.
    
- En déployant plusieurs appliances de connecteur de nuage au sein d’un seul site RTPC, autoriser pour une haute disponibilité.
    
Cette rubrique présente les sites RTC. Pour plus d’informations sur la planification de vos sites RTPC, voir [planifier des sites de nuage lien édition RTPC](plan-for-cloud-connector-edition-pstn-sites.md).
  
Vous pouvez déployer les topologies de nuage connecteur suivants :
  
- Une seule appliance de nuage lien édition par site de RTPC. Cette topologie n’est recommandée que pour les évaluations car elle ne fournit pas de haute disponibilité.
    
- Plusieurs applications d’édition de connecteur de nuage par site RTPC pour fournir une haute disponibilité. 
    
- Plusieurs sites de RTPC avec plusieurs applications d’édition de connecteur de nuage pour assurer l’évolutivité avec une disponibilité élevée. Vous pouvez déployer jusqu’à 200 sites.
    
Lors de la planification de votre topologie, tenez compte des points suivants :
  
- Nuage connecteur 2.0 et les versions ultérieures, un site RTPC peut avoir jusqu'à 16 équipements de connecteur de nuage. Les versions antérieures prennent en charge jusqu'à 4 appliances par site. 
    
- Il existe deux types de configurations matérielles testées avec le connecteur du nuage : 
    
  - La plus grande version est capable de traiter un large volume d'appels simultanés et est prise en charge dans tous les types d'environnements de production.
    
  - La version réduite est destinée à une exécution sur du matériel bas de gamme et peut être utilisée pour des évaluations ou pour des sites traitant peu d'appels. Si vous déployez la version réduite de Cloud Connector, vous devez continuer à tenir compte de la configuration matérielle requise pour la production (par exemple, deux sources d'alimentation).
    
- Si le connecteur de nuage version 2.0 ou ultérieure et que vous déployez la configuration maximale de 16 appliances (avec un matériel plus important), votre site RTPC peut gérer jusqu'à 8 000 appels simultanés. Si vous déployez la version réduite, la limite est de 800. 
    
    Vous devez également dédier quelques appliances à la haute disponibilité. Il est recommandé de dédier au moins une appliance à la haute disponibilité.
    
  - Avec la version 2, si vous déployez une configuration 15 + 1, votre site RTPC peut gérer jusqu'à 7 500 appels simultanés.
    
  - Si vous disposez d'une version antérieure et que vous déployez la configuration maximum, 3 + 1 (avec du matériel plus conséquent), votre site PSTN peut gérer jusqu'à 1 500 appels simultanés. Si vous déployez la version réduite, la limite est de 150.
    
-  S’il vous avez besoin de davantage d’appels par site RTC, vous pouvez développer votre installation en déployant des sites RTC supplémentaires au même emplacement.
    
> [!NOTE]
> Sauf si le contraire, les diagrammes et les exemples ci-dessous supposent que vous utilisez la version plus grande du connecteur de nuage. 
  
### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>Appliance unique Cloud Connector dans un site PSTN unique

Le diagramme suivant montre une seule appliance édition de connecteur de nuage au sein d’un seul site RTPC. Notez que le connecteur du nuage se compose de quatre des machines virtuelles installées sur un ordinateur hôte physique qui se trouve dans un réseau de périmètre pour des raisons de sécurité.
  
![Cloud Connector avec un site RTC](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)
  
### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>Plusieurs appliances Cloud Connector dans un site PSTN unique

 Pour les besoins de haute disponibilité et d’évolutivité, vous pouvez choisir d’avoir plusieurs éditions de connecteur de nuage au sein d’un seul site RTPC comme illustré dans le diagramme suivant. Dans ce cas, tenez compte des points suivants :
  
- Les appels sont distribués dans un ordre aléatoire entre les instances Cloud Connector d’un pool.
    
- Pour des raisons de planification des capacités, vous devez envisager la possibilité de gérer la charge si une ou plusieurs appliances Cloud Connector passent en mode hors connexion, en fonction des calculs suivants :
    
  - **Cases N+1.** Pour la version plus grande du connecteur du nuage, N + 1 cases prend en charge 500\*d’appels simultanés avec une disponibilité de 99,8 % N.
    
    Pour la version réduite du connecteur du nuage, N + 1 cases prend en charge 50\*d’appels simultanés avec une disponibilité de 99,8 % N.
    
  - **Cases N+2.** Pour la version plus grande du connecteur du nuage, N + 2 zones de prise en charge de 500\*d’appels simultanés avec une disponibilité de 99,9 % N.
    
    Pour la version réduite du connecteur du nuage, N + 2 zones prend en charge 50\*d’appels simultanés avec une disponibilité de 99,9 % N.
    
![Deux connecteurs de cloud dans 1 site RTC](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)
  
### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>Plusieurs sites RTC avec une ou plusieurs instances Cloud Connector par site

Vous pouvez également opter pour la création de plusieurs sites RTC avec une ou plusieurs instances Cloud Connector sur chaque site. Si votre site RTPC atteint la limite d’appels simultanés, vous pouvez ajouter un autre site RTPC pour gérer la charge.
  
Une configuration à plusieurs sites RTC permet également de fournir une connectivité aux passerelles les plus proches de vos utilisateurs. Supposez, par exemple, que vous utilisiez des passerelles RTC à Seattle et Amsterdam. Vous pouvez déployer deux sites RTC, l’un à Seattle, l’autre à Amsterdam, et affecter des utilisateurs de sorte qu’ils utilisent le site RTC le plus proche. Les utilisateurs de Seattle seront acheminés vers le site RTC et les passerelles de Seattle, tandis que les utilisateurs d’Amsterdam seront acheminés vers le site RTC et les passerelles d’Amsterdam :
  
![Version Cloud Connector dans 2 sites RTC](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)
  
## <a name="requirements-for-deployment"></a>Configuration requise pour le déploiement
<a name="BKMK_Requirements"> </a>

Avant le déploiement de Cloud connecteur Edition, assurez-vous que vous disposez des éléments suivants pour votre environnement :
  
- **Pour l’ordinateur hôte :** Machines virtuelles de connecteur de nuage doit être déployé sur du matériel dédié exécutant Windows Server 2012 R2 Datacenter edition (anglais) avec le rôle Hyper-V est activé.
    
    Pour la version 2.0 et les suivantes, la carte réseau de l'ordinateur hôte attachée au commutateur de réseau entreprise de Skype Entreprise doit disposer d'une adresse IP configurée dans le même sous-réseau que les ordinateurs du réseau d'entreprise de Cloud Connector.  
    
- Pour les versions 2.1 et version ultérieures, l’application hôte doit avoir.NET Framework 4.6.1 ou version ultérieure. 
    
- **Pour les ordinateurs virtuels :** Une image de Windows Server 2012 R2 ISO (en anglais) (.iso). L’ISO est convertie aux disques durs virtuels pour les machines virtuelles qui exécutera Skype pour connecteur de Cloud Business Edition.
    
- Le matériel nécessaire pour prendre en charge l’installation de 4 ordinateurs virtuels pour chaque édition de connecteur de nuage dans votre déploiement. Les configurations ci-dessous sont recommandées :
    
  - 64 bits double processeur, six principaux (12 noyaux réel), 2,50 gigahertz (GHz) ou supérieur
    
  - 64 giga-octets (Go) de mémoire vive (RAM) ECC  
    
  - Quatre disques SAS de 600 Go (ou supérieur) à 10 000 tr/min, 128 Mo de mémoire cache, 6 Gbits/s, mis en œuvre dans une configuration RAID 5
    
  - Trois cartes réseau 1 Gbits/s RJ45 haut débit
    
- Si vous choisissez de déployer la version réduite du nuage connecteur Edition qui prend en charge jusqu'à 50 appels simultanés, vous devez le matériel suivant :
    
  - Intel i7 4790 quad core avec Intel 4600 Graphics (pas besoin de carte graphique haut de gamme)
    
  - 32 Go DDR3-1600 non ECC
    
  - 2 : 1 To 7200 RPM Serial Attached SCSI III (6 Go/s), RAID 0
    
  - 2 : Ethernet 1 Go/s (RJ45)
    
- Si un serveur proxy est requis sur un ordinateur hôte à des fins de navigation sur Internet, appliquez les modifications de configuration suivantes :
    
  - Pour contourner le serveur proxy, spécifiez les paramètres de WinHTTP Proxy avec votre serveur proxy et une liste de contournement, notamment le 192.168.213 ». \*« réseau utilisé par les services de gestion du connecteur Cloud et par Skype pour le sous-réseau du réseau d’entreprise entreprise tel que défini dans le fichier CloudConnector.ini. Dans le cas contraire, connectivité de gestion échoue et empêcher le déploiement et la récupération automatique du connecteur de nuage. L’exemple suivant est un exemple de commande de configuration winhttp : netsh winhttp définie la liste de contournement proxy « 10.10.10.175:8080 » = »\*".local" ; 1. \*, 172.20. \*; 192.168.218. \*'\<local\>».
    
  - Spécifiez les paramètres proxy par ordinateur au lieu de les spécifier par utilisateur. Téléchargements de connecteur de nuage échoue dans le cas contraire. Vous pouvez spécifier des paramètres proxy par ordinateur en modifiant le registre ou via le paramètre de stratégie de groupe comme suit :
    
  - **Registre :** Paramètres de HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet] DWORD : 00000000 de ProxySettingsPerUser
    
  - **La stratégie de groupe :** Ordinateur\>les modèles d’administration\>composants Windows\> Internet Explorer : paramètres de Proxy de rendre par ordinateur (et non par utilisateur)
    
- Système PBX/jonction ou SBC/passerelle qualifié (un minimum de deux passerelles est recommandé).
    
    Cloud Connector prend en charge les mêmes contrôleurs SBC (Session Border Controller) que ceux certifiés pour Skype Entreprise. Pour plus d’informations, consultez [Infrastructure de téléphonie pour Skype pour les entreprises](https://technet.microsoft.com/en-us/office/dn947483.aspx). 
    
- Un compte d’administrateur de serveur local avec les autorisations nécessaires pour installer et configurer Hyper-V sur les serveurs hôtes. Le compte doit disposer des autorisations d’administrateur sur le serveur local sur lequel Hyper V est installé et configuré.
    
- Lors du déploiement, vous devrez créer un compte d’administrateur de domaine avec les autorisations de création et de publication de la topologie dans le domaine Cloud Connector.  
    
- Enregistrements DNS externes définis dans le fichier CloudConnector.ini inclus dans le package d'installation :
    
  - Enregistrement DNS externe pour le service Edge d’accès du composant de bord ; par exemple, ap.\<nom de domaine\>. Vous aurez besoin d’un enregistrement par site RTC. Cet enregistrement doit contenir les adresses IP de tous les bords pour ce site.
    
- Un locataire d’Office 365 avec toutes les enregistrements DNS et SRV créés.
    
    > [!IMPORTANT]
    > Lorsque vous intégrez votre client avec l’édition de connecteur de nuage, l’utilisation du suffixe de domaine par défaut,. onmicrosoft.com, comme un domaine SIP de votre organisation n’est pas supportée. > Vous ne pouvez pas utiliser le sip. \<Nom de domaine\> comme nom de votre accès de bord nuage connecteur d’interface proxy car cet enregistrement DNS est utilisé par Office 365. 
  
- Un certificat pour le serveur Edge externe obtenu auprès d'une autorité de certification publique (CA).
    
- Des règles de pare-feu visant à autoriser le trafic via les ports nécessaires ont été définies. 
    
- Une connexion à Internet pour l’ordinateur hôte et les machines virtuelles. Connecteur de nuage télécharge un logiciel à partir d’Internet ; Par conséquent, vous devez fournir de passerelle et les informations du serveur DNS afin que la machine hôte de connecteur de nuage et les ordinateurs virtuels puissent se connecter à Internet et télécharger le logiciel nécessaire.
    
- Un module PowerShell en client distant installé sur l'ordinateur hôte.
    
- Les informations d'identification d'administrateur de Skype Entreprise Office 365 pour exécuter PowerShell en client distant. 
    
    > [!IMPORTANT]
    > L'authentification multi-facteur NE DOIT PAS être activée pour le compte administrateur. 
  
> [!NOTE]
> Déploiement de connecteur de nuage est uniquement pris en charge sur la plate-forme de virtualisation de Microsoft Hyper-V. Les autres plateformes, comme VMware et Amazon Web Services, ne le prennent pas en charge. 
  
> [!NOTE]
> Le Guide de configuration matérielle minimale pour exécuter le connecteur du nuage est basé sur la capacité matérielle de base (cœurs, MHz, Go, etc.) avec une mémoire tampon pour prendre en compte des handicaps performances incorporelle enfouies dans l’architecture de n’importe quel ordinateur. Microsoft a exécuté une vérification de la pire charge de cas sur du matériel disponible dans le commerce en s’appuyant sur une aide minimum. La qualité multimédia et les performances du système sont vérifiées. Officiels partenaires solution matérielle-logicielle de connecteur de nuage de Microsoft ont des implémentations spécifiques de connecteur de nuage matériel sur lequel ils ont testé indépendamment des performances et attenant à la pertinence de leur matériel pour répondre aux exigences de qualité et de la charge. 
  
> [!NOTE]
> Les appareils produits par AudioCodes et Sonus ont modifié le code et fonctionné sur une version de serveurs de Windows Server Standard. Ces appareils sont pris en charge. 
  
## <a name="information-you-need-to-gather-before-deployment"></a>Informations à recueillir avant le déploiement
<a name="BKMK_PlanDeployment"> </a>

Avant de commencer votre déploiement, vous devez déterminer sa taille, les domaines SIP pris en charge et les informations de configuration pour chacun des sites PSTN à déployer. Pour commencer, vous devez :
  
- Identifier tous les domaines SIP qui seront servis par ce déploiement fondée sur les URI SIP utilisé dans votre société. 
    
- déterminer le nombre de sites PSTN à déployer ;
    
- Vérifiez que vous disposez du matériel nécessaire pour prendre en charge de quatre ordinateurs virtuels vous allez installer pour chaque édition de connecteur de nuage. 
    
Pour chaque site RTPC que vous envisagez de déployer, vous devez :
  
- Créer des noms pour tous les composants de la solution matérielle-logicielle chaque connecteur de nuage (voir [déterminer les paramètres de déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)).
    
- Définir des plages de ports (reportez-vous à la rubrique [Ports et protocoles](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)) ;  
    
- créer des enregistrements DNS externes pour le composant Edge (reportez-vous à la rubrique [Requirements for deployment](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)) ;
    
- déterminer les exigences en matière de certificats pour le composant Edge (reportez-vous à la rubrique [Certificate requirements](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)).
    
### <a name="ports-and-protocols"></a>Ports et protocoles
<a name="BKMB_Ports"> </a>

Lors de la définition des plages de ports multimédias, gardez les points suivants à l’esprit :
  
- Les clients utilisent toujours la plage de port 50000 à 50019 pour le trafic multimédia, cette plage est prédéfinie dans Skype pour les professionnels en ligne et ne peut pas être modifiée.
    
- Le composant de médiation utilise, par défaut, la plage de ports comprise entre 49 152 et 57 500 pour le trafic multimédia. Toutefois, est établie via un pare-feu interne et, pour des raisons de sécurité, vous pouvez limiter cette plage de ports de votre topologie. Vous devrez compter jusqu’à 4 ports par appel. Si vous souhaitez limiter le nombre de ports entre le composant de médiation et la passerelle RTC, vous devrez également configurer la plage de ports correspondante sur la passerelle.
    
- Vous devez déployer le connecteur du Cloud dans un réseau de périmètre. Cela signifie que vous aurez deux pare-feu : 
    
  - Le premier pare-feu est externe, entre Internet et votre réseau de périmètre.
    
  - Le deuxième pare-feu est interne entre le réseau de périmètre et votre réseau interne. 
    
    Vos clients peuvent se trouver sur Internet ou sur le réseau interne :  
    
  - Les clients sur Internet se connectent à votre réseau téléphonique public commuté (RTC) via le pare-feu externe, à travers le composant Edge.
    
  - Les clients du réseau interne seront connecte via le pare-feu interne pour le composant de médiation dans le réseau de périmètre, ce qui fera le trafic à la passerelle SBC ou PSTN. 
    
    Vous devez donc ouvrir des ports dans les deux pare-feu.  
    
Les tableaux ci-dessous décrivent les ports et les plages de ports pour les pare-feu externe et interne.
  
Ce tableau indique les ports et les plages de ports permettant la communication entre les clients sur le réseau interne et le composant de médiation :
  
**Pare-feu interne**



|**Adresse IP source**|**Destination IP**|**Port source**|**Port de destination**|
|:-----|:-----|:-----|:-----|
|Composant de connecteur médiation de nuage  <br/> |Passerelle SBC/PSTN  <br/> |Indifférente  <br/> |TCP 5060\*\*  <br/> |
|Passerelle SBC/PSTN  <br/> |Composant de connecteur médiation de nuage  <br/> |Indifférente  <br/> |TCP 5068/TLS 5067  <br/> |
|Composant de connecteur médiation de nuage  <br/> |Passerelle SBC/PSTN  <br/> |UDP, 49 152-57 500  <br/> |Tout\*\*\*  <br/> |
|Passerelle SBC/PSTN  <br/> |Composant de connecteur médiation de nuage  <br/> |Tout\*\*\*  <br/> |UDP, 49 152-57 500  <br/> |
|Composant de connecteur médiation de nuage  <br/> |Clients internes  <br/> |TCP, 49 152-57 500\*  <br/> |TCP 50 000 à 50 019  <br/> (Facultatif)  <br/> |
|Composant de connecteur médiation de nuage  <br/> |Clients internes  <br/> |UDP, 49 152-57 500\*  <br/> |UDP 50 000 à 50 019  <br/> |
|Clients internes  <br/> |Composant de connecteur médiation de nuage  <br/> |TCP 50 000 à 50 019  <br/> |TCP, 49 152-57 500\*  <br/> |
|Clients internes  <br/> |Composant de connecteur médiation de nuage  <br/> |UDP 50 000 à 50 019  <br/> |UDP 49 152-57 500\*  <br/> |
   
\*Il s’agit de la plage de ports par défaut pour le composant de médiation. Pour obtenir un flux d’appels optimal, quatre ports par appel sont nécessaires.
  
\*\*Ce port doit être configuré sur la passerelle SBC/RTPC ; 5060 est un exemple. Vous pouvez configurer d’autres ports sur votre passerelle SBC/RTC.
  
\*\*\*Notez que vous pouvez également limiter la plage de ports sur votre SBC/passerelle si autorisé par le fabricant SBC/Gateway.
  
Pour des raisons de sécurité, vous pouvez limiter la plage de ports pour le composant de médiation à l’aide de l’applet de commande [Set-CsMediationServer](https://docs.microsoft.com/powershell/module/skype/set-csmediationserver?view=skype-ps) .
  
Par exemple, la commande suivante limite le nombre de ports qui utilise le composant de médiation pour le trafic multimédia 50 000-station 51 000 pour l’audio (entrée et sortie). Avec cette configuration, le composant de médiation pourra traiter 250 appels simultanés. Notez que vous souhaiterez peut-être également limiter cette plage sur la passerelle SBC/RTC :
  
```
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

Pour récupérer le nom du composant de médiation et de voir les ports par défaut, vous pouvez utiliser l’applet de commande [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps) comme suit :
  
```
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

Le tableau suivant montre les ports et plages de ports permettant la communication entre le composant nuage bord du connecteur pour le pare-feu externe. Ce tableau indique la configuration minimale recommandée.
  
Dans ce cas, media du trafic internet passe via le bord en ligne comme suit : utilisateur de point de terminaison--\>en ligne bord--\>bord du connecteur de nuage :
  
**Pare-feu externe - configuration minimale**



|**Adresse IP source**|**Destination IP**|**Port source**|**Port de destination**|
|:-----|:-----|:-----|:-----|
|Indifférente  <br/> |Interface externe du nuage connecteur bord  <br/> |Indifférente  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externe du nuage connecteur bord  <br/> |Indifférente  <br/> |Indifférente  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externe du nuage connecteur bord  <br/> |Indifférente  <br/> |Indifférente  <br/> |TCP 80  <br/> |
|Interface externe du nuage connecteur bord  <br/> |Indifférente  <br/> |Indifférente  <br/> |UDP 53  <br/> |
|Interface externe du nuage connecteur bord  <br/> |Indifférente  <br/> |Indifférente  <br/> |TCP 53  <br/> |
|Interface externe du nuage connecteur bord  <br/> |Indifférente  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Indifférente  <br/> |Interface externe du nuage connecteur bord  <br/> |TCP 50 000 à 59 999  <br/> |TCP 443  <br/> |
|Indifférente  <br/> |Interface externe du nuage connecteur bord  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Interface externe du nuage connecteur bord  <br/> |Indifférente  <br/> |TCP 50 000 à 59 999  <br/> |TCP 443  <br/> |
   
Le tableau suivant répertorie les ports et plages de ports permettant la communication entre le composant nuage bord du connecteur pour le pare-feu externe. Ce tableau montre la solution recommandée.
  
Dans ce cas tous les supports du point de terminaison dans internet circulent directement au composant nuage bord du connecteur. Le chemin d’accès de média sera un utilisateur de Point de terminaison -\> bord du connecteur de nuage.
  
> [!NOTE]
> Cette solution ne fonctionne pas si le point de terminaison utilisateur est protégé par une fonction de conversion d'adresses réseau (NAT) symétrique. 
  
**Pare-feu externe - configuration recommandée**


|**Adresse IP source**|**Destination IP**|**Port source**|**Port de destination**|
|:-----|:-----|:-----|:-----|
|Indifférente  <br/> |Interface externe du nuage connecteur bord  <br/> |Indifférente  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externe du nuage connecteur bord  <br/> |Indifférente  <br/> |Indifférente  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externe du nuage connecteur bord  <br/> |Indifférente  <br/> |Indifférente  <br/> |TCP 80  <br/> |
|Interface externe du nuage connecteur bord  <br/> |Indifférente  <br/> |Indifférente  <br/> |UDP 53  <br/> |
|Interface externe du nuage connecteur bord  <br/> |Indifférente  <br/> |Indifférente  <br/> |TCP 53  <br/> |
|Interface externe du nuage connecteur bord  <br/> |Indifférente  <br/> |TCP 50 000 à 59 999  <br/> |Indifférente  <br/> |
|Interface externe du nuage connecteur bord  <br/> |Indifférente  <br/> |UDP 3 478 ; UDP 50 000 à 59 999  <br/> |Indifférente  <br/> |
|Indifférente  <br/> |Interface externe du nuage connecteur bord  <br/> |Indifférente  <br/> |TCP 443 ; TCP 50 000 à 59 999  <br/> |
|Indifférente  <br/> |Interface externe du nuage connecteur bord  <br/> |Indifférente  <br/> |UDP 3478 ; UDP 50 000 à 59 999  <br/> |
   
### <a name="host-internet-connectivity-requirements"></a>Conditions requises de l'hôte pour la connexion Internet
<a name="BKMB_Ports"> </a>

L’ordinateur hôte doit être en mesure d’atteindre des ressources externes pour installer, mettre à jour et gérer avec succès les connecteur de nuage. Le tableau suivant indique les destinations et ports nécessaires entre l’ordinateur hôte et les ressources externes. 
  
||||||||
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Direction  <br/> |Adresse IP source  <br/> |Adresse IP de destination  <br/> |Port source  <br/> |Port de destination  <br/> |Protocole  <br/> |Objectif  <br/> |
|Sortant  <br/> |Nuage connecteur HIPS  <br/> |indifférente  <br/> |indifférente  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|Sortant  <br/> |Nuage connecteur HIPS  <br/> |indifférente  <br/> |indifférente  <br/> |80, 443  <br/> |TCP  <br/> |Liste de révocation de certificats (CRL)  <br/> |
|Sortant  <br/> |Hôte de Connectorr de nuage IPs  <br/> |indifférente  <br/> |indifférente  <br/> |80, 443  <br/> |TCP  <br/> |Mise à jour du connecteur de nuage  <br/> Skype Entreprise Online  <br/> Administrateur PowerShell  <br/> Windows Update  <br/> |
   
Si des règles plus restrictives sont nécessaires, consultez les URL suivantes sur liste blanche :
  
- [URL de liste de révocation de certificats](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) dans [les URL d’Office 365 et de plages d’adresses IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- Mise à jour de Windows : [Comment faire pour configurer un pare-feu pour les mises à jour logicielles](https://technet.microsoft.com/en-us/library/bb693717.aspx)
    
- Skype pour entreprise en ligne Admin PowerShell : \*. online.lync.com
    
    Si une exclusion de proxy est nécessaire pour cette destination, vous devrez l'ajouter à la liste de contournement WinHTTP.
    
- [Centre de téléchargement](https://aka.ms/CloudConnectorInstaller)de la mise à jour du connecteur de nuage :, [https://go.microsoft.com](https://go.microsoft.com), et[http://download.microsoft.com](http://download.microsoft.com)
    
### <a name="dns-name-resolution-for-the-edge-component"></a>Résolution des noms DNS pour le composant Edge
<a name="BKMB_Ports"> </a>

Le composant de bord doit résoudre les noms externes des services Office 365 et les noms internes d’autres composants du connecteur du nuage. 
  
Chaque composant Edge est un ordinateur à plusieurs connexions avec des interfaces interne et externe. Connecteur de nuage déploie des serveurs DNS sur le composant de contrôleur de domaine dans le réseau de périmètre. Vous pouvez pointer le serveur de transport Edge pour le serveur DNS dans le périmètre de toutes les résolutions de noms, mais vous devez activer le serveur en nuage connecteur DNS résoudre les noms externes en définissant une zone DNS contenant un ou plusieurs enregistrements DNS A pour les requêtes externes qui référence le nom recherches sur d’autres serveurs DNS publics. 
  
Dans le fichier .ini, si vous définissez comme domaine SIP le nom de domaine complet des passerelles du même domaine, la zone faisant autorité pour ce domaine SIP sera créée dans le serveur DNS au sein du périmètre. Si le serveur de transport Edge est pointé vers ce serveur DNS pour résoudre les noms, bord résoudra jamais le _sipfederationtls. \<votre_domaine\> enregistrement DNS, qui est requis pour les flux d’appels. Dans ce cas, Microsoft vous recommande de vous fournissez un serveur DNS sur l’interface externe de bord pour les recherches de noms Internet de résoudre que chaque bord doit utiliser un fichier Hosts pour résoudre d’autres noms de composant de connecteur de nuage à des adresses IP.
  
> [!NOTE]
> Pour des raisons de sécurité, il est recommandé que vous ne pointez pas le serveur DNS de connecteur de Cloud pour les serveurs internes dans le domaine de la production pour la résolution de nom. 
  
### <a name="determine-deployment-parameters"></a>Définition des paramètres de déploiement
<a name="BKMK_SiteParams"> </a>

Vous devez d'abord définir les paramètres de déploiement communs suivants :
  

|**Élément**|**Description**|**Remarques**|
|:-----|:-----|:-----|
|Domaines SIP  <br/> |Du URI SIP en cours d’utilisation par les utilisateurs de la société. Fournit tous les domaines SIP pris en charge par ce déploiement. Vous pouvez disposer de plusieurs domaines SIP.  <br/> ||
|Nombre de sites RTC  <br/> |Nombre de sites RTC que vous allez déployer.  <br/> ||
   
Pour chaque site RTC que vous envisagez de déployer, vous devrez rassembler les informations suivantes avant de commencer le déploiement. Vous devrez fournir ces informations lorsque vous mettez à jour le fichier CloudConnector.ini.
  
Lorsque vous configurez les informations de la passerelle, gardez à l’esprit les points suivants :
  
- Si vous disposez d’une seule passerelle, supprimez la section « deuxième passerelle » dans le fichier .ini. S’il y a plus de deux passerelles, suivez le format existant pour en ajouter de nouvelles.
    
- Assurez-vous que l’adresse IP et le port de la (des) passerelle(s) sont corrects.
    
- Pour permettre une haute disponibilité de la passerelle RTC, conservez la passerelle secondaire ou ajoutez des passerelles.
    
(Facultatif) Pour limiter les numéros d’appels sortants, mettez à jour la valeur LocalRoute.
  


|**Paramètres de site**|**Description**|**Remarques**|
|:-----|:-----|:-----|
|Nom de domaine de la machine virtuelle  <br/> |Nom de domaine pour les composants internes du connecteur de nuage. Ce domaine doit être différent du domaine de production. Il peut s'agir du même nom sur toutes les appliances de Cloud Connector.  <br/> Nom dans le fichier .ini : « VirtualMachineDomain »  <br/> |.domaine local recommandé.   <br/> |
|Nom de contrôleur de domaine de connecteur cloud  <br/> |Nom du contrôleur de domaine.   <br/> Nom dans le fichier .ini : « NomServeur »  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> |
|Connecteur domaine contrôleur IP/masque de sous-réseau du nuage  <br/> |Adresse IP du contrôleur de domaine.   <br/> Nom dans le fichier .ini : « IP »  <br/> ||
|Noms de domaine complet des services en ligne O365  <br/> |Doit être la valeur par défaut dans la plupart des cas pour l’instance de O365 à l’échelle mondiale.  <br/> Nom dans le fichier .ini : « OnlineSipFederationFqdn »  <br/> ||
|Nom du site  <br/> |Skype pour le nom du site Business ; par exemple, Seattle.  <br/> Nom dans le fichier .ini : « SiteName »  <br/> Pour la version 1.4.1 et les suivantes, le nom du site doit être différent pour chaque site, et le nom doit correspondre au site RTC, s’il existe, défini dans Office 365. Notez que les sites RTC sont automatiquement créés au moment de l’inscription de la première appliance dans un site.  <br/> ||
|HardwareType  <br/> Version 1.4.1 et suivantes  <br/> |Type de matériel. La valeur par défaut est Normal. Vous pouvez également la définir sur Minimum.  <br/> ||
|Indicatif du pays/de la région  <br/> |Indicatif du pays/de la région pour la numérotation.  <br/> Nom dans le fichier .ini : « Code pays »  <br/> ||
|Ville  <br/> |Ville (facultatif).  <br/> Nom dans le fichier .ini : « Ville »  <br/> ||
|État  <br/> |État (facultatif).  <br/> Nom dans le fichier .ini : « État »  <br/> ||
|Adresse IP des machines virtuelles de base  <br/> |L’adresse IP de la machine base virtuelle temporaire qui sera utilisée pour créer la VHDX pour tous les ordinateurs virtuels de connecteur de nuage. Cette IP doit se trouver dans le même sous-réseau de réseau de périmètre d'entreprise défini dans l'étape suivante et requiert un accès Internet. Veillez à définir la passerelle par défaut et le DNS d'entreprise routable à Internet.  <br/> Nom dans le fichier .ini : « BaseVMIP »  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> Version 1.4.1 et suivantes  <br/> |L'adresse des services de mises à jour de serveur Windows (WSUS), un serveur intranet qui héberge les mises à jour depuis Microsoft Update.  <br/> Vous pouvez ne rien écrire si vous n'avez pas besoin de WSUS.   <br/> ||
|Masque de sous-réseau pour réseau interne  <br/> |Connecteur de nuage configure un réseau IP pour la communication interne entre les composants du connecteur du nuage. Edge doit également être connecté à un autre sous-réseau qui permet la connexion à Internet.  <br/> Nom dans le fichier .ini : « CorpnetIPPrefixLength » sous « Paramètres d’un pool de réseau de la machine virtuelle »  <br/> ||
|Masque de sous-réseau pour réseau externe   <br/> |Pour le réseau externe du composant Edge.  <br/> Nom dans le fichier .ini : « InternetIPPrefix » sous « Paramètres d’un pool de réseau de la machine virtuelle »  <br/> ||
|Nom du commutateur pour réseau interne  <br/> |Nom de commutateur qui sera utilisé pour le réseau interne de connecteur de nuage.  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nom dans le fichier .ini : « CorpnetSwitchName » sous « paramètres d’un pool de réseau de la machine virtuelle  <br/> ||
|Nom du commutateur pour réseau externe  <br/> |Nom de commutateur qui sera utilisé pour le réseau externe de connecteur de nuage.  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nom dans le fichier .ini : « InternetSwitchName » sous « paramètres d’un pool de réseau de la machine virtuelle  <br/> ||
|Passerelle par défaut pour le réseau interne  <br/> |Cette passerelle doit fournir un accès à Internet (Internet requiert également la définition du serveur DNS) et sera configuré sur les interfaces internes des composants de connecteur en nuage.  <br/> Nom dans le fichier .ini : « CorpnetDefaultGateway » sous « paramètres d’un pool de réseau de la machine virtuelle  <br/> ||
|Passerelle par défaut pour l’interface externe du composant Edge  <br/> |Sera configurée sur l’interface externe du composant Edge.  <br/> Nom dans le fichier .ini : « InternetDefaultGateway » sous « paramètres d’un pool de réseau de la machine virtuelle  <br/> ||
|Serveur DNS pour réseau interne  <br/> |Sera configuré sur l’interface interne de la machine virtuelle temporaire. Doit de fournir la résolution de nom pour les noms Internet. Connexion Internet échoue sans fournir un serveur DNS, et de déploiement ne se terminera pas.  <br/> Nom dans le fichier .ini : « CorpnetDNSIPAddress » sous « paramètres d’un pool de réseau de la machine virtuelle  <br/> ||
|Serveur DNS pour interface externe du composant Edge  <br/> |Sera configuré sur l’interface externe du serveur Edge.  <br/> Nom dans le fichier .ini : « InternetDNSIPAddress » sous « paramètres d’un pool de réseau de la machine virtuelle  <br/> ||
|Nom du commutateur de gestion  <br/> |Commutateur de gestion est un commutateur temporaire qui est créé automatiquement, et qui sera utilisé pour la configuration du connecteur de nuage pendant le déploiement. Il sera également déconnecté automatiquement après le déploiement. Il doit être un sous-réseau différent de celui de tout autre réseau utilisé dans le connecteur de nuage.  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nom dans le fichier .ini : « ManagementSwitchName » sous « paramètres d’un pool de réseau de la machine virtuelle  <br/> ||
|Masque de sous-réseau/adresse du sous-réseau de gestion  <br/> |Sous-réseau de gestion est un sous-réseau temporaire qui est créé automatiquement, et qui sera utilisé pour la configuration du connecteur de nuage pendant le déploiement. Il sera également déconnecté automatiquement après le déploiement. Il doit être un sous-réseau différent de celui de tout autre réseau utilisé dans le connecteur de nuage.  <br/> Les noms dans le fichier .ini : « ManagementIPPrefix » et « ManagementIPPrefixLength » sous « paramètres d’un pool de réseau de la machine virtuelle  <br/> ||
|Machine de magasin central de gestion (MCG)  <br/> |Nom de domaine complet unique utilisé pour le magasin central de gestion (CMS). Le nom du domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nom dans le fichier .ini : « Nomserveur » sous « paramètres pour Central Management Service principal  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> (Nom du pool CMS = Nom du serveur)  <br/> |
|Adresse IP de la machine du magasin central de gestion  <br/> |Adresse IP de serveur CMS (interne dans le réseau de périmètre).  <br/> Nom de fichier INI : « IP », sous « paramètres pour Central Management Service principal  <br/> ||
|Nom du partage de fichiers   <br/> |Nom de partage de fichier à créer sur le serveur CMS pour Skype pour les données de réplication d’entreprise (par exemple, CmsFileStore).  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nom dans le fichier .ini : « CmsFileStore » sous « paramètres pour Central Management Service principal  <br/> ||
|Composant de médiation nom du Pool  <br/> |Nom du pool du composant de médiation. Entrez un nom Netbios uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nom dans le fichier .ini : « PoolName » sous « Paramètres d’un pool de serveurs de médiation »  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> |
|Nom de composant de médiation  <br/> |Nom du composant de médiation 1. Entrez un nom Netbios uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.   <br/> Nom dans le fichier .ini : « Nomserveur » sous « Paramètres d’un pool de serveurs de médiation »  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> |
|Adresse IP de l’ordinateur du composant médiation  <br/> |Interne Corpnet IP pour composant de médiation (interne dans le réseau de périmètre).  <br/> Nom dans le fichier .ini : « IP » sous « Paramètres d’un pool de serveurs de médiation »  <br/> ||
|Nom interne du pool du serveur Edge  <br/> |Nom du pool du composant Edge. Entrez un nom Netbios uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nom dans le fichier .ini : « InternalPoolName » sous « Paramètres d’un pool de serveurs Edge »  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> |
|Nom interne du serveur Edge  <br/> |Nom du composant Edge. Entrez un nom Netbios uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.   <br/> Nom dans le fichier .ini : « InternalServerName » sous « Paramètres d’un pool de serveurs Edge »  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> |
|Adresse IP interne du serveur Edge   <br/> |Composant de IP du bord interne de périmètre réseau pour communiquer avec d’autres composants du connecteur du nuage.  <br/> Nom dans le fichier .ini : « InternalServerIPs » sous « Paramètres d’un pool de serveurs Edge »  <br/> ||
|Nom externe du pool d’accès  <br/> |Nom du serveur Edge d’accès, par exemple, AP. Ce nom doit correspondre au nom indiqué pour le certificat SSL. Entrez un nom Netbios uniquement. Le nom de domaine SIP sera utilisé pour générer le nom de domaine complet. Un nom de pool externe sera utilisé pour tous les composants de bord dans le pool. Un pool de bord accès est requis par le site de RTPC.  <br/> Nom dans le fichier .ini : « ExternalSIPPoolName » sous « Paramètres d’un pool de serveurs Edge »  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> « sip » est réservé et ne peut donc pas être utilisé comme nom.  <br/> Le nom de domaine complet généré doit correspondre au nom fourni pour le certificat SSL.   <br/> |
|Adresse IP externe de Edge d’accès  <br/> |Composant de IP du bord externe - l’adresse IP publique si aucun NAT n’est disponible, ou traduit IP (Veuillez préciser les deux adresses si mappé).  <br/> Nom dans le fichier .ini : « ExternalSIPIPs » sous « Paramètres d’un pool de serveurs Edge »  <br/> ||
|Nom du serveur relais multimédia  <br/> |Nom du serveur Edge du serveur relais multimédia audio/vidéo, par exemple, MR. Un seul nom de pool externe sera utilisé pour tous les composants Edge d’un pool. Un pool de relais multimédia de bord est requis par le site de RTPC.  <br/> Nom dans le fichier .ini : « ExternalMRFQDNPoolName » sous « Paramètres d’un pool de serveurs Edge »  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> |
|Adresse IP externe du bord de relais multimédia  <br/> |Actuellement seule IP est pris en charge, il s’agit de la même adresse IP comme Edge d’accès, IP public ou mappé (Veuillez préciser les deux adresses si mappé). Peut être la même adresse en tant que composant de bord IP d’accès périphérie externe. Remarque Si le contour est derrière un NAT, vous devez également spécifier la valeur pour le paramètre suivant.  <br/> Nom dans le fichier .ini : « ExternalMRIPs » sous « Paramètres d’un pool de serveurs Edge »  <br/> ||
|IP de Media relais périphérie externe (si le contour est derrière un NAT)  <br/> |Si votre Edge est protégé par une traduction d’adresse réseau, vous devez également spécifier l’adresse publique du périphérique NAT.  <br/> Nom dans le fichier .ini : « ExternalMRPublicIPs » sous « Paramètres d’un pool de serveurs Edge »  <br/> ||
|Passerelle 1 marque et le modèle de la voix  <br/> |Indiquez la marque et le modèle de la passerelle SBC/vocale. Notez que vous pouvez connecter un périphérique ou un SIP trunk à partir de la liste des périphériques testés à [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP).  <br/> ||
|2 Assurez-vous de passerelle et le modèle (copier cette ligne si vous avez plus de 2 passerelles) la voix  <br/> |Indiquez la marque et le modèle de la passerelle vocale. Notez que vous pouvez vous connecter un périphérique à partir de la liste des périphériques testés à [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP).  <br/> ||
|Nom de la passerelle 1 voix  <br/> |Utilisé pour générer le nom de domaine complet de la machine avec le domaine AD. Nécessaire si TLS est utilisé entre le composant de médiation et la passerelle vocale. Si vous ne prévoyez pas d’utiliser le nom de domaine complet, par exemple, TLS n’est pas nécessaire ou passerelle vocale ne prennent en charge la connexion à l’aide du nom de domaine complet (uniquement IP) — spécifiez.  <br/> ||
|Voix de passerelle 2 nom (copie cette ligne si vous avez plus de 2 passerelles)  <br/> |Utilisé pour générer le nom de domaine complet de la machine avec le domaine AD. Nécessaire si TLS est utilisé entre le composant de médiation et la passerelle vocale. Si vous ne prévoyez pas d’utiliser le nom de domaine complet, par exemple, TLS n’est pas nécessaire ou passerelle vocale ne prennent en charge la connexion à l’aide du nom de domaine complet (uniquement IP) — spécifiez.  <br/> ||
|Adresse IP de la passerelle 1 voix  <br/> |Adresse IP de la passerelle vocale.  <br/> ||
|Adresse IP de passerelle 2 (copier cette ligne si vous avez plus de 2 passerelles) la voix  <br/> |Adresse IP de la passerelle vocale.  <br/> ||
|Voix de passerelle 1 Port # (copie cette ligne si vous avez plus de 2 passerelles)  <br/> |Port écouté par la jonction SIP de la passerelle vocale, par exemple, 5 060.  <br/> ||
|Passerelle 2 la voix de Port  <br/> |Port écouté par la jonction SIP de la passerelle vocale, par exemple, 5 060.  <br/> ||
|Protocole de passerelle 1 voix pour le trafic SIP  <br/> |TCP ou TLS.  <br/> ||
|Protocole de passerelle de 2 la voix pour le trafic SIP (copie cette ligne si vous avez plus de 2 passerelles)  <br/> |TCP ou TLS.  <br/> ||
|Plage de ports multimédias externes pour le trafic à destination et en provenance du composant Edge  <br/> |Plage de ports TCP/UDP pour le trafic multimédia à destination et en provenance de l’interface externe du composant Edge. Doit toujours commencer à 50 000. Pour plus d’informations, voir « Ports et protocoles ».  <br/> |50000-59 999  <br/> |
|Plage de communiquer dans le composant de médiation via le pare-feu interne de port média  <br/> |Plage de ports UDP que le composant de médiation utilisera pour communiquer avec les clients et de passerelles (ports de recommandation 4 par appel).  <br/> ||
|Plage de communiquer dans Skype pour client d’entreprise via le pare-feu interne de port média  <br/> |Ne peut pas être modifiée en raison de la planification. Les ports doivent être ouverts dans le pare-feu interne pour communiquer entre Skype pour les clients professionnels au sein du réseau interne et le composant de médiation.  <br/> |50 000 à 50 019  <br/> |
|Mot de passe du certificat public  <br/> |Doit être indiqué dans le script.  <br/> ||
|Mot de passe administrateur en mode sans échec  <br/> Version 1.4.2 uniquement  <br/> |Mot de passe administrateur en mode sans échec pour le domaine Cloud Connector interne  <br/> ||
|Mot de passe administrateur de domaine de connecteur de nuage  <br/> Version 1.4.2 uniquement  <br/> |Mot de passe de nuage lien administrateur de domaine (différent de votre domaine de la production). Le nom d’utilisateur est Administrator. Vous ne pouvez pas le modifier.  <br/> ||
|Mot de passe administrateur des machines virtuelles  <br/> Version 1.4.2 uniquement  <br/> |Utilisé pour configurer le réseau de gestion lors du déploiement.  <br/> Le nom d'utilisateur est Administrator. Vous ne pouvez pas le modifier.   <br/> ||
|CABackupFile  <br/> Version 2.0 et ultérieures  <br/> |Utilisé pour enregistrer le Service d’autorité de Certification à partir du serveur Active Directory dans un fichier lors du déploiement de plusieurs solutions matérielles-logicielles dans un site connecteur du nuage. Être sûr d’utiliser le même mot de passe pour tous les matériels au sein d’un site de connecteur de nuage afin d’importer le fichier de sauvegarde d’autorité de certification vers le nouveau ajouté solution matérielle-logicielle.  <br/> ||
|CCEService  <br/> Version 2.0 et ultérieures  <br/> |Utilisé pour le service de gestion Cloud Connector ; nécessite l'accès à l'annuaire de site Cloud Connector. Assurez-vous d'utiliser le même mot de passe pour toutes les appliances sur un même site Cloud Connector.   <br/> ||
|Administrateur client Office 365  <br/> | Le compte est utilisé par Cloud Connector pour mettre à jour et gérer les paramètres du client pour Cloud Connector : <br/>  Version 2.0 et versions ultérieure : informations d’identification pour un Office 365 dédié compte avec Skype pour les droits d’administrateur de l’entreprise. <br/>  Version antérieure à 2.0 : informations d'identification d'un compte Office 365 dédié disposant des droits d'administrateur client global. <br/> ||
|Activer la prise en charge de REFER.  <br/> |Cela déterminera si la prise en charge de SIP REFER est activée ou désactivée sur la configuration de la jonction de votre IP/système PBX. La valeur par défaut est True. Si votre passerelle IP/PBX prend en charge la prise en charge de REFER, veuillez laisser la valeur True. Dans le cas contraire, cette valeur doit être redéfinie sur False. Si vous n’êtes pas sûr si votre passerelle prend en charge la référence, consultez [qualifié IP-PBX et passerelles](https://technet.microsoft.com/en-us/office/dn788945).  <br/> ||
|EnableFastFailoverTimer  <br/> Version 2.0 et ultérieures  <br/> |Avec la valeur par défaut « True » si les appels sortants ne sont pas traités par la passerelle dans les 10 secondes qu’ils seront acheminées vers la passerelle suivante disponible ; s’il n’existe aucun puits supplémentaires l’appel va être supprimé automatiquement.  <br/> Cependant, dans une organisation dont les réseaux et les réponses de la passerelle sont lents, ou lorsque la procédure d'établissement d'appel dépasse les 10 secondes, cela peut entraîner l'abandon inutile des appels.   <br/> Lors de l’appel à certains pays, par exemple les Émirats arabes unis Afghanistan, appel établissant le processus peut prendre plus de 10 secondes. Vous devez affecter la valeur False si vous rencontrez des problèmes similaires. N’oubliez pas de modifier le paramètre correspondant sur le SBC connecté ou une passerelle.  <br/> Les valeurs peuvent être « True » ou « False ». La valeur par défaut est « True ».  <br/> ||
|ForwardCallHistory  <br/> Version 2.0 et ultérieures  <br/> | Ce paramètre est utilisé pour les en-têtes SIP utilisés pour signaler l'appelant initial dans des scénarios de sonnerie simultanée et de transfert d'appel. Définir le paramètre sur « True » entraîne l'activation de deux en-têtes SIP :<br/>  History-Info <br/>  Referred-By <br/>  L’en-tête historique-Info est utilisé pour le re-ciblage des requêtes SIP et « minutieuses un mécanisme standard pour capturer les informations de l’historique de demande pour permettre à un large éventail de services pour les réseaux et les utilisateurs finaux » ([RFC 4244 - point 1.1](http://www.ietf.org/rfc/rfc4244.txt)). En ce qui concerne les interfaces de jonction de Cloud Connector, elles sont utilisées dans des scénarios de sonnerie simultanée et de transfert d'appel.  <br/>  Les valeurs peuvent être « True » ou « False ». La valeur par défaut est « False ».<br/> ||
|Transfert PAI  <br/> Version 2.0 et ultérieures  <br/> |PAI est une extension privée SIP qui permet aux serveurs SIP affirmer l’identité des utilisateurs authentifiés. Pour le fournisseur de jonction SIP, PAI peut servir à des fins à facturer dans le cas où un historique-Info et visés par les en-têtes ne sont pas présents. Lorsque le transfert P-affirmée-Identity est activée dans la configuration, le serveur de médiation transmettra les en-têtes PAI avec SIP &amp; Tel URI de connecteur de nuage sur la jonction SIP. Le serveur de médiation transmettra à en-têtes PAI avec de URI tel &amp; numéros E.164 reçus uniquement sur le SIP trunk au connecteur de nuage. Le serveur de médiation transmettra également les en-têtes de confidentialité reçus dans les deux sens. Si le SIP de demande envoyé par le serveur de médiation inclut un en-tête de confidentialité de l’écran - « confidentialité : id » conjointement avec l’en-tête PAI, puis l’identité prétendue devant rester confidentielles en dehors du domaine d’approbation de réseau.  <br/> Les valeurs peuvent être « True » ou « False ». La valeur par défaut est « False ».  <br/> ||
   
### <a name="certificate-requirements"></a>Exigences en matière de certificats
<a name="BKMK_Certs"> </a>

Chaque composant Edge nécessite un certificat délivré par une autorité de certification publique. Les certificats doivent disposer d’une clé privée exportable pour pouvoir être copiés d’un composant Edge à l’autre. Pour respecter ces exigences, vous devrez choisir entre les options ci-après et indiquer le nom de sujet (SN) et un autre nom de sujet (SAN) pour le certificat :
  
 **Si vous disposez d'un domaine SIP unique :**
  
- **Option 1.** Le nom de sujet doit contenir le nom du pool affecté aux composants Edge. Notez que le nom du sujet ne peut pas être sip.sipdomain.com car ce nom est réservé à la Skype en ligne pour composant de bord d’entreprise. L'autre nom de sujet doit contenir sip.sipdomain.com et le nom du pool Edge d'accès :
    
  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, 
acessedgepoolnameforsite1.sipdomain.com 

  ```

- 
    
    **Option 2.** Si vous souhaitez utiliser un certificat générique unique sur tous les serveurs de pool de bord vous déployez, puis vous pouvez utiliser une entrée de SAN générique de \*. sipdomain.com au lieu du nom du pool de bord dans le certificat. Le nom de sujet peut être le nom d’un des pools Edge d’accès que vous avez déployés :
    
  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com

  ```

    > [!NOTE]
    > Vous ne devez pas créer une entrée DNS externe pour le sip. \<sipdomain\>.com, car ce nom appartient au déploiement d’Office 365. 
  
> [!NOTE]
> Si vous souhaitez utiliser un certificat unique pour tous les pools Edge déployés dans votre organisation et ne pouvez pas utiliser un certificat générique comme défini dans l'option 2, vous devrez alors inclure le nom de domaine complet pour tous les pools Edge déployés dans le nom SAN dans le certificat.  
  
 **Si vous disposez de plusieurs domaines SIP :**
  
Vous devez ajouter sip.sipdomain.com pour chaque domaine SIP, ainsi que le nom des pools Edge d’accès par domaine (il peut s’agir d’un pool physique avec des noms différents). Vous trouverez ci-dessous un exemple d’entrées SN et SAN dans un scénario comportant plusieurs domaines SIP : 
  
- **Option 1.** Le nom du sujet doit contenir le nom de pool que vous avez affecté des composants de bord. Notez que le nom du sujet ne peut pas être sip.sipdomain.com car ce nom est réservé à la Skype en ligne pour composant de bord d’entreprise. L'autre nom de sujet doit contenir sip.sipdomain.com et le nom du pool Edge d'accès :
    
  ```
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com,
 sip.sipdomain2.com, acessedgepoolnameforsite1.sipdomain1.com 

  ```

- 
    
    **Option 2.** Si vous souhaitez utiliser un certificat générique unique sur tous les serveurs de pool de bord vous déployez, puis vous pouvez utiliser une entrée de SAN générique de \*. sipdomain.com au lieu du nom du pool de bord dans le certificat. Le nom de sujet peut être le nom d’un des pools Edge d’accès que vous avez déployés :
    
  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com, SAN = *.sipdomain1.com 
  ```

    > [!NOTE]
    > Vous ne devez pas créer une entrée DNS externe pour le sip. \<sipdomain\>.com, car ce nom appartient au déploiement d’Office 365. 
  
Dans le cadre d'un déploiement, vous pouvez utiliser le tableau suivant :
  
|**Option**|**Description**|**Remarques**|
|:-----|:-----|:-----|
|Quelle option allez-vous utiliser pour votre déploiement ?  <br/> |Option 1 ou 2  <br/> ||
|SN  <br/> |Indique le nom de sujet du certificat  <br/> ||
|SAN  <br/> |Indique l'autre nom de sujet du certificat  <br/> ||
   
Si vous utilisez TLS entre la passerelle et le serveur de médiation, vous devrez obtenir le certificat racine ou la chaîne de certificats complète pour le certificat assigné à la passerelle.
  
## <a name="dial-plan-considerations"></a>Aspects relatifs au plan de numérotation
<a name="BKMK_DailPlan"> </a>

Cloud Connector requiert l'utilisation d'un plan de numérotation en ligne. Pour plus d’informations sur la configuration d’un plan d’appel en ligne, reportez-vous à la section [Quels sont les plans de numérotation PSTN appel ?](https://support.office.com/en-US/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b)
  
## <a name="high-availability-considerations"></a>Considérations relatives à la haute disponibilité
<a name="BKMK_HA"> </a>

Lorsque vous déployez le nuage lien édition pour une haute disponibilité, vous déployez au moins deux dispositifs qui agissent en tant que sauvegarde les uns aux autres. Chaque solution matérielle-logicielle se compose de quatre composants : bord, médiation, magasin Central de gestion (MCG) et contrôleur de domaine.
  
En règle générale, si un composant au sein d’une solution matérielle-logicielle tombe en panne, Édition de connecteur de nuage peut continuer à traiter les appels, mais vous devez prendre en compte les éléments suivants :
  
- **Mediation, CMS et les considérations relatives au composant du contrôleur de domaine**
    
    Supposons que le composant du contrôleur de domaine ou du magasin central de gestion d’une appliance ne fonctionne pas. L’appliance peut toujours traiter les appels entrants et sortants, mais si vous relancez un composant de médiation lorsque le composant du contrôleur de domaine ou du magasin central de gestion est inaccessible, la médiation ne fonctionnera pas. Vous ferez face à la même situation si vous relancez le composant du magasin central de gestion lorsque le contrôleur de domaine est en panne. 
    
    **Recommandation :** Avant de redémarrer des composants, vérifiez la disponibilité des autres composants de la solution matérielle-logicielle.
    
- **Considérations relatives au composant Edge**
    
    Si le composant Edge d'une appliance n'est pas disponible, le comportement des appels entrants et sortants changera, de la façon suivante :
    
  - **Appel de sortant**— un appel à partir de votre utilisateur d’Internet à un réseau RTPC.
    
    Le mécanisme de distribution d'appels dans le cloud identifiera le fait que l'un des composants Edge est hors service et acheminera tous les appels vers une autre appliance, afin que l'appel sortant aboutisse.
    
  - **Appel d’entrant**— un appel à partir du réseau PSTN à un utilisateur qui est dans un réseau local ou Internet.
    
     Si le composant Edge de l’appliance qui a reçu l’appel ne fonctionne pas, les appels entrants dans cette appliance ne fonctionneront pas, car le composant de médiation ne peut pas rediriger l’appel vers le composant Edge dans l’autre appliance.
    
    **Recommandation :** Avez un système de surveillance en place. Après avoir identifié un dysfonctionnement du composant bord, mettez hors tension tous les composants de la solution matérielle-logicielle où le composant de bord n’est pas disponible.
    
## <a name="cloud-connector-media-flow"></a>Trafic multimédia de Cloud Connector
<a name="BKMK_MediaFlow"> </a>

Les schémas suivants détaillent le flux d’un appel entrant et sortant via le nuage lien édition. Ces informations sont utiles pour comprendre comment la connexion est établie.
  
Sur la première illustration, un utilisateur interne passe un appel sortant, comme suit :
  
1. Dave, un utilisateur hébergé en ligne, mais qui se trouve actuellement sur le réseau interne, appelle un utilisateur RTC externe.
    
2. Voies de circulation SIP à Skype pour l’activité en ligne.
    
3. Skype pour entreprise en ligne effectue une recherche de numéro inversée du nombre. La recherche de numéro inversée échoue car ce numéro n’appartient pas à tous les utilisateurs le Skype pour l’organisation de l’entreprise.
    
4. L’appel est acheminé vers le composant Edge (trafic SIP et multimédia par le biais du composant Online Edge dans un premier temps, puis le trafic multimédia vers le composant de médiation par le biais du pare-feu interne).
    
5. Si l’itinéraire existe, le composant Edge relaie le trafic vers le composant de médiation dans le réseau de périmètre.
    
6. Le composant de médiation envoie le trafic vers la passerelle RTC.
    
![Flux de média sortant pour Cloud Connector](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)
  
Sur l’illustration ci-dessous, un utilisateur interne reçoit un appel entrant comme suit :
  
1. La passerelle RTC reçoit un appel pour l’utilisateur Dave, qui est hébergé en ligne, mais se trouve actuellement sur le réseau interne.
    
2. Le trafic SIP est acheminé vers le composant de médiation.
    
3. Le composant de médiation envoie le trafic SIP au composant bord et puis il accède à Skype pour l’activité en ligne.
    
4. Skype pour entreprise en ligne effectue une recherche de numéro inversée du numéro et détecte qu’il s’agit d’utilisateur Dave.
    
5. La signalisation SIP est envoyée vers tous les points de présence de Dave.
    
6. Le trafic multimédia est établi entre la passerelle et le composant de médiation et entre le composant de médiation et le point de terminaison.
    
![Flux de média entrant pour Cloud Connector](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)
  
## <a name="monitoring-and-troubleshooting"></a>Analyse et résolution des problèmes
<a name="BKMK_Monitor"> </a>

Le mécanisme d'analyse et de résolution des problèmes est installé automatiquement avec chaque appliance Cloud Connector. Le mécanisme détecte les événements suivants :
  
- Un ou plusieurs ordinateurs d'une appliance Cloud Connector ne sont pas connectés à un commutateur virtuel interne ou internet.
    
- Un ou plusieurs ordinateurs d'une appliance Cloud Connector sont en état Enregistré ou Arrêté.
    
- Les services ne sont pas exécutés. 
    
  Si un des événements suivants est détecté, l’appliance de connecteur du nuage tout est épuisée et marqué comme hors connexion pour empêcher la tentative d’établissement d’appels à un matériel défectueux. Les fonctionnalités de récupération automatique de Cloud Connector restaureront ensuite les services et marqueront l'appliance comme étant en ligne. Si la récupération automatique échoue pour une raison quelconque, consultez [résoudre les problèmes de votre déploiement de connecteur de nuage](troubleshoot-your-cloud-connector-deployment.md).
    
  - Sur la machine virtuelle du magasin central de gestion :  
    
     - Agent réplicateur maître Skype Entreprise
    
     - Agent réplicateur de réplicas Skype Entreprise
    
  - Sur la machine virtuelle du serveur de médiation :
    
     - Agent réplicateur de réplicas Skype Entreprise
    
     - Serveur de médiation Skype Entreprise
    
  - Sur la machine virtuelle du serveur Microsoft Edge
    
     - Agent réplicateur de réplicas Skype Entreprise
    
     -  Serveur Edge d'accès Skype Entreprise
    
     - Serveur Edge audio/vidéo Skype Entreprise
    
     - Serveur d'authentification audio/vidéo Skype Entreprise
    
     - Serveur Edge de conférence web Skype Entreprise
    
- La règle entrante du pare-feu Windows pour « CS RTCSRV » sur Microsoft Edge, « CS RTCMEDSRV » sur le serveur de médiation est désactivée.
    
Cloud Connector 2.1 et les versions ultérieures prennent en charge la surveillance de Cloud Connector avec Operations Management Suite (OMS). Pour plus d’informations, voir [Analyseur de connecteur de Cloud à l’aide de la Suite de gestion des opérations (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)
  
## <a name="for-more-information"></a>Pour plus d'informations
<a name="BKMK_MoreInfo"> </a>

Pour plus d'informations, voir les articles suivants :
  
- [Planification de votre système téléphonique dans les solutions Office 365 (Cloud PBX)](plan-your-phone-system-cloud-pbx-solution.md)
    
- [Configurer et gérer Skype pour connecteur de Cloud Business Edition](configure-skype-for-business-cloud-connector-edition.md)
    
- [Planifier le contournement de média dans le nuage lien édition](plan-for-media-bypass-in-cloud-connector-edition.md)
    
- [Déployer le contournement de média dans le nuage lien édition](deploy-media-bypass-in-cloud-connector.md)
    

