---
title: Planification pour Skype Entreprise, version Cloud Connector
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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6ce0e580-8c4a-45de-a54f-e39e438335d6
description: Obtenez des informations sur la version Cloud Connector de Skype Entreprise, un ensemble de machines virtuelles (VM) qui met en œuvre une connectivité PSTN locale avec un système téléphonique d'Office 365 (Cloud PBX).
ms.openlocfilehash: 4d03d8ea6936ad906de01a5b478fce01d62113c4
ms.sourcegitcommit: d12a9f2d10093e24d4af54ce6044b512e7e3787e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454134"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Planification pour Skype Entreprise, version Cloud Connector

Obtenez des informations sur la version Cloud Connector de Skype Entreprise, un ensemble de machines virtuelles (VM) qui met en œuvre une connectivité PSTN locale avec un système téléphonique d'Office 365 (Cloud PBX).

Si vous ne figure pas une existante Lync Server ou les Skype pour le déploiement de serveur d’entreprise dans le nuage connecteur Edition est peut-être la solution idéale pour votre organisation. Si vous êtes toujours étudier qui système téléphonique dans les solutions Office 365 est adaptée à votre entreprise, voir [solutions de téléphonie Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions).

Ce document décrit les exigences de nuage connecteur Edition et les topologies prises en charge et vous aide à planifier votre déploiement en nuage connecteur Edition. Veillez à lire cette rubrique avant de configurer votre environnement en nuage connecteur. Lorsque vous êtes prêt à déployer et configurer le nuage connecteur Edition, voir [configurer et gérer des Skype pour édition dans le nuage connecteur](configure-skype-for-business-cloud-connector-edition.md).

Nuage connecteur Edition 2.1 est désormais disponible. Si vous n'avez pas encore effectué la mise à niveau vers la version 2.1, reportez-vous à la rubrique [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md). Vous trouverez le fichier d’installation [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).

> [!NOTE]
> Microsoft prend en charge la version précédente du nuage connecteur Edition pendant 60 jours après la publication d’une nouvelle version. Microsoft prend en charge la version 2.0.1 pendant 60 jours après la sortie de la version 2.1 pour vous laisser le temps de la mettre à niveau. Toutes les versions antérieures à 2.0.1 ne sont plus prises en charge.

Nuage connecteur Edition est un hybride offre qui se compose d’un ensemble de marchandises Machines virtuelles (VM) qui implémentent la connectivité RTPC locale avec un système téléphonique dans Office 365. En déployant un Skype minimal pour la topologie Business Server dans un environnement virtualisé, les utilisateurs de votre organisation qui sont hébergés dans le nuage peuvent recevoir les services de PBX à partir du cloud Microsoft, mais une connectivité PSTN est fournie par le biais de la voix sur site existant infrastructure.

![Diagramme de topologie montrant Cloud PBX Gateway reliant Cloud PBX à un déploiement local de Skype Entreprise.](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

Comme Cloud Connector vous permert d'intégrer le système téléphonique dans les services d'Office 365 à votre environnement téléphonique actuel (par exemple PBX, des appareils analogiques et des centres d'appels), vous pouvez implémenter une migration progressive vers le système téléphonique d'Office 365.

Par exemple, imaginons que votre entreprise possède un centre d'appels sophistiqué avec des fonctionnalités spécifiques que le système téléphonique d'Office 365 ne fournit pas. Vous pouvez choisir de garder la solution existante pour les utilisateurs du centre d'appels, mais de déplacer les autres utilisateurs vers le système téléphonique d'Office 365.

Cloud Connector se chargera du routage entre les utilisateurs hébergés localement et ceux hébergés en ligne, et vous pouvez choisir d'utiliser votre propre fournisseur PSTN avec le système téléphonique d'Office 365.

Considérez les points suivants lorsque vous planifiez votre déploiement dans le nuage connecteur Edition :

- Pour utiliser le connecteur sur le nuage pour tirer parti des solutions de voix dans le nuage, vous devez inscrire pour un client Office 365 qui inclut le système téléphonique dans Office 365. Si vous ne possédez pas encore de client Office 365, vous pouvez découvrir comment vous inscrire ici : [Office 365 Entreprise](https://products.office.com/en-us/business/office). Notez que vous devez inscrire pour un plan incluant Skype pour Business Online.

- Pour inscrire appliances nuage connecteur avec le Skype pour le service Business Online et exécuter les applets de commande différents, nuage connecteur 2.0 et versions ultérieur nécessite un compte Office 365 dédié avec le Skype pour des droits d’administrateur de client de Business. Les versions de Cloud Connector antérieures à 2.0 requièrent un compte Office 365 dédié disposant des droits d'administrateur client global.

- Nuage connecteur ne nécessite pas complète locale Skype pour le déploiement de serveur d’entreprise.

    Actuellement, nuage connecteur ne peut pas coexister avec Lync ou Skype pour les entreprises serveurs locaux. Si vous souhaitez déplacer Lync existant ou Skype pour les utilisateurs professionnels vers Office 365 et conserver fournissant locale téléphonie à vos utilisateurs, pensez à système téléphonique dans Office 365 avec une connectivité locale à l’aide d’un Skype existant pour le déploiement de serveur d’entreprise. Pour plus d’informations, voir [planifier votre système téléphonique dans les solutions Office 365 (en nuage PBX)](plan-your-phone-system-cloud-pbx-solution.md) et [Planifier le système téléphonique dans Office 365 avec une connectivité PSTN dans Skype pour Business Server local](plan-phone-system-with-on-premises-pstn-connectivity.md).

- Si vous avez une précédente Skype pour le déploiement de Lync Server ou de l’entreprise, et vous avez étendu le schéma, il est inutile nettoyer le schéma pour le déploiement dans le nuage connecteur, dans la mesure où vous avez supprimé toutes les Skype pour les composants Lync Server ou de l’entreprise à partir de votre environnement.

- Vos utilisateurs sont hébergés en ligne.

- Si votre organisation a configuré la synchronisation Active Directory (DirSync), tous les comptes des utilisateurs planifiés pour la voix hybride doivent être créés en premier lieu localement, puis synchronisés vers le cloud.

- Vous pouvez conserver votre opérateur RTC actuel, si nécessaire.

- Si vous souhaitez fournir la conférence rendez-vous pour les utilisateurs hébergés sur le nuage connecteur, vous pouvez acheter des licences de conférence PSTN ou retenues offre de conférence Audio à partir de Microsoft.

- La conférence Audio licence (ou retenues offre) également requis pour l’escalade d’appel. Si un Skype pour l’utilisateur reçoit un appel d’un utilisateur PSTN externe et souhaite ajouter un participant plus à cet appel (transformer l’appel à une conférence), l’escalade sera effectuée via le service de conférence Audio de Microsoft.

- Cloud Connector 2.0 et les version ultérieures prennent désormais en charge la déviation du trafic. Le contournement de média permet au client d’envoyer des données multimédia directement au saut suivant Public réseau de téléphonique commuté (RTC) — une passerelle ou un contrôleur de Session en périphérie (SBC) — et d’éliminer le composant nuage connecteur Edition à partir du chemin d’accès des médias. Pour plus d’informations, voir [Plan for media ignorer dans le nuage connecteur Edition](plan-for-media-bypass-in-cloud-connector-edition.md).

- Cloud Connector 2.1 et les versions ultérieures prennent en charge la surveillance de Cloud Connector avec Operations Management Suite (OMS). Pour plus d’informations, reportez-vous à la rubrique [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md).

- Nuage connecteur est disponible dans tous les pays où Office 365 entreprise E5 est disponible. Toutefois, en raison des réglementations diverses, nuage connecteur ne peut pas être configurée Si l’emplacement du client est défini à un des pays suivants : Algérie, Bangladesh, Botswana, Brunei, Cameroun, côte d’Ivoire, Ghana, Liban, Macao, Maurice, Namibie, Paraguay, Sénégal.

Cette rubrique contient les sections suivantes :

- [Composants de la version Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [Topologies de la version Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [Configuration requise pour le déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [Informations que nécessaires pour recueillir avant le déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [Aspects relatifs au plan de numérotation](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [Considérations relatives à la haute disponibilité](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [Trafic multimédia de Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [Analyse et résolution des problèmes](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [Pour plus d'informations](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>Composants de la version Cloud Connector
<a name="BKMK_Components"> </a>

Avec le nuage connecteur Edition, vous déployez un ensemble d’ordinateurs virtuels marchandises qui contiennent un Skype minimal pour la topologie du serveur d’entreprise, constitué d’un composant de serveur Edge, composant de médiation et un rôle du magasin Central de gestion (CMS). Vous allez également installer un contrôleur de domaine est requis pour le fonctionnement interne du nuage connecteur. Ces services sont configurés pour un environnement hybride avec votre client Office 365 qui inclut Skype pour Business Online services.

![Composants de la version Cloud Connector](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

Composants du nuage connecteur fournissent les fonctionnalités suivantes :

- **Composant edge** : Communication entre la topologie sur site et les services en ligne passe par le composant de périphérie, qui inclut les composants suivants :

  - **Serveur Edge d’accès** - en fournit SIP routage entre le déploiement local et Skype pour Business en ligne.

  - **Serveur relais multimédia** - fournit le routage des médias entre le composant de médiation et d’autres points de terminaison multimédia.

  - **L’authentification du relais multimédia / MRAS** -génère des jetons d’accès au serveur relais multimédia.

- **Le routage sortant** - fournit équilibrage du trafic entre les passerelles voix ou SBC connecté à un connecteur dans le nuage. Les appels seront répartis équitablement entre tous les SBC et passerelles connectés à l'appliance Cloud Connector.

    Fournit un routage vers les passerelles en fonction des stratégies. Seules les politiques mondiales dépendant des numéros PSTN de destination (trafic sortant) sont prises en charge.

- **Rôle du magasin de gestion centrale (CMS)** - inclut le magasin de configuration pour les composants de la topologie, y compris le transfert de fichiers CMS.

- Le **réplica du magasin central de gestion (CMS)** - synchronise les informations de configuration de la base de données CMS globale sur le serveur de rôle CMS.

- **Contrôleur de domaine** - nuage connecteur Active Directory Domain Services pour stocker tous les paramètres globaux et les groupes nécessaires pour déployer les composants du connecteur sur le nuage. Une forêt sera créée pour chaque application connecteur sur le nuage. Le contrôleur de domaine ne doit pas avoir toutes les connexions à la production de Active Directory. Les services Active Directory comprennent :

  - Services de domaine Active Directory

  - Services de certificats Active Directory permettant d'émettre des certificats internes

- **Composant de médiation** - protocole de mappage de passerelle SIP implémente et les médias entre Skype pour les passerelles Business et PSTN. Inclut un réplica CMS qui synchronise la configuration à partir de la base de données CMS globale.

## <a name="cloud-connector-edition-topologies"></a>Topologies de la version Cloud Connector
<a name="BKMK_Topologies"> </a>

Dans le cadre de cet article, nous les appellerons « sites PSTN ». Un site RTC est une combinaison de matériel de nuage connecteur, déployé au même emplacement et avec les passerelles PSTN courantes connectés. Les sites PSTN permettent d'effectuer les opérations suivantes :

- Fournissez une connectivité aux passerelles les plus proches de vos utilisateurs.

- Permettre une évolutivité en déployant plusieurs applications dans le nuage connecteur au sein d’un ou plusieurs sites PSTN.

- Autoriser pour une haute disponibilité en déployant plusieurs applications dans le nuage connecteur au sein d’un seul site PSTN.

Cette rubrique présente les sites PSTN. Pour plus d'informations sur la planification de vos sites PSTN, reportez-vous à la rubrique [Plan for Cloud Connector Edition PSTN sites](plan-for-cloud-connector-edition-pstn-sites.md).

Vous pouvez déployer les topologies de nuage connecteur suivantes :

- Une solution de nuage connecteur Edition unique par site PSTN. Cette topologie n'est recommandée que pour les évaluations car elle ne fournit pas de haute disponibilité.

- Plusieurs applications dans le nuage connecteur Edition par site PSTN pour fournir une haute disponibilité.

- Plusieurs sites PSTN avec plusieurs applications dans le nuage connecteur Edition pour fournir une évolutivité avec une haute disponibilité. Vous pouvez déployer jusqu'à 200 sites.

Lors de la planification de votre topologie, tenez compte des points suivants :

- Avec le nuage connecteur 2.0 et versions ultérieures, un site PSTN peut avoir jusqu'à 16 appliances nuage connecteur. Les versions antérieures prennent en charge jusqu'à 4 appliances par site.

- Il existe deux types de configurations matérielles testées avec le connecteur sur le nuage :

  - La plus grande version est capable de traiter un large volume d'appels simultanés et est prise en charge dans tous les types d'environnements de production.

  - La version réduite est destinée à une exécution sur du matériel bas de gamme et peut être utilisée pour des évaluations ou pour des sites traitant peu d'appels. Si vous déployez la version réduite de Cloud Connector, vous devez continuer à tenir compte de la configuration matérielle requise pour la production (par exemple, deux sources d'alimentation).

- Si vous avez nuage connecteur 2.0 ou version ultérieure et déployez la configuration maximale de 16 appliances (avec matériel plus important), votre site PSTN peut gérer jusqu'à 8 000 appels simultanés. Si vous déployez la version réduite, la limite est de 800.

    Vous devez également dédier quelques appliances à la haute disponibilité. Il est recommandé de dédier au moins une appliance à la haute disponibilité.

  - Avec la version 2, si vous déployez une configuration 15 + 1, votre site PSTN peut gérer jusqu'à 7 500 appels simultanés.

  - Si vous disposez d'une version antérieure et que vous déployez la configuration maximum, 3 + 1 (avec du matériel plus conséquent), votre site PSTN peut gérer jusqu'à 1 500 appels simultanés. Si vous déployez la version réduite, la limite est de 150.

-  Si vous avez besoin de davantage d'appels par site PSTN, vous pouvez développer votre installation en déployant des sites PSTN supplémentaires au même emplacement.

> [!NOTE]
> Sauf contraire, les schémas et les exemples suivants supposent que vous utilisez la version la plus grande du nuage connecteur.

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>Appliance unique Cloud Connector dans un site PSTN unique

Le diagramme suivant illustre une solution de nuage connecteur Edition unique au sein d’un seul site PSTN. Notez que dans le nuage connecteur se compose de quatre ordinateurs virtuels installés sur un ordinateur hôte physique qui se trouve dans un réseau de périmètre pour des raisons de sécurité.

![Cloud Connector avec un site RTC](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>Plusieurs appliances Cloud Connector dans un site PSTN unique

 Pour l’évolutivité et à des fins de haute disponibilité, vous pouvez choisir d’avoir plusieurs éditions de connecteur dans le nuage au sein d’un seul site PSTN comme indiqué dans le diagramme suivant. Dans ce cas, tenez compte des points suivants :

- Les appels sont distribués dans un ordre aléatoire entre les instances Cloud Connector d'un pool.

- Pour des raisons de planification des capacités, vous devez envisager la possibilité de gérer la charge si une ou plusieurs appliances Cloud Connector passent en mode hors connexion, en fonction des calculs suivants :

  - **Cases N+1.** Pour la version la plus grande du nuage connecteur, N + 1 cases prennent en charge 500\*avec une disponibilité 99,8 % d’appels simultanés N.

    Pour la version la plus petite du nuage connecteur, N + 1 cases prend en charge 50\*avec une disponibilité 99,8 % d’appels simultanés N.

  - **Cases N+2.** Pour la version la plus grande du nuage connecteur, N + 2 zones prennent en charge 500\*appels simultanés N avec une disponibilité de 99,9 %.

    Pour la version la plus petite du nuage connecteur, N + 2 zones prend en charge 50\*appels simultanés N avec une disponibilité de 99,9 %.

![Deux connecteurs de cloud dans 1 site RTC](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>Plusieurs sites PSTN avec une ou plusieurs instances Cloud Connector par site

Vous pouvez également opter pour la création de plusieurs sites PSTN avec une ou plusieurs versions de Cloud Connector sur chaque site. Si votre site PSTN atteint la limite d'appels simultanés, vous pouvez ajouter un autre site PSTN pour gérer la charge.

Une configuration à plusieurs sites PSTN permet également de fournir une connectivité aux passerelles les plus proches de vos utilisateurs. Supposez, par exemple, que vous utilisiez des passerelles PSTN à Seattle et Amsterdam. Vous pouvez déployer deux sites PSTN, l'un à Seattle, l'autre à Amsterdam, et affecter des utilisateurs de sorte qu'ils utilisent le site PSTN le plus proche. Les utilisateurs de Seattle seront acheminés vers le site PSTN et les passerelles de Seattle, tandis que les utilisateurs d'Amsterdam seront acheminés vers le site PSTN et les passerelles d'Amsterdam :

![Version Cloud Connector dans 2 sites RTC](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>Configuration requise pour le déploiement
<a name="BKMK_Requirements"> </a>

Avant de déployer sur le nuage connecteur Edition, assurez-vous que les paramètres suivants pour votre environnement :

- **Pour l’ordinateur hôte-** Ordinateurs virtuels de nuage connecteur doit être déployé sur du matériel dédié exécutant Windows Server 2012 R2 Datacenter edition (en anglais) avec le rôle Hyper-V est activé.

    Pour la version 2.0 et les suivantes, la carte réseau de l'ordinateur hôte attachée au commutateur de réseau entreprise de Skype Entreprise doit disposer d'une adresse IP configurée dans le même sous-réseau que les ordinateurs du réseau d'entreprise de Cloud Connector. 

- Pour les versions 2.1 et version ultérieures, l’application hôte .NET Framework 4.6.1 doit être ou version ultérieure.

- **Pour les ordinateurs virtuels :** Une image de Windows Server 2012 R2 ISO (en anglais) (.iso). La norme ISO est convertie au disques durs virtuels pour les ordinateurs virtuels qui s’exécuteront Skype pour l’édition de connecteur Business Cloud.

- Le matériel nécessaire pour prendre en charge l’installation des ordinateurs 4 virtuels pour chaque version de connecteur nuage dans votre déploiement. Les configurations ci-dessous sont recommandées :

  - biprocesseur 64 bits, six core (12 cœurs réels), 2,50 gigahertz (GHz) ou supérieur

  - 64 giga-octets (Go) de mémoire vive (RAM) ECC 

  - Quatre disques SAS de 600 Go (ou supérieur) à 10 000 tr/min, 128 Mo de mémoire cache, 6 Gbits/s, mis en œuvre dans une configuration RAID 5

  - Trois cartes réseau 1 Gbits/s RJ45 haut débit

- Si vous choisissez de déployer la version la plus petite de nuage connecteur Edition qui prend en charge jusqu'à 50 appels simultanés, vous devez le matériel suivant :

  - Intel i7 4790 quad core avec Intel 4600 Graphics (pas besoin de carte graphique haut de gamme)

  - 32 Go DDR3-1600 non ECC

  - 2 : 1 To 7200 RPM Serial Attached SCSI III (6 Go/s), RAID 0

  - 2 : Ethernet 1 Go/s (RJ45)

- Si un serveur proxy est requis sur un ordinateur hôte à des fins de navigation sur Internet, appliquez les modifications de configuration suivantes :

  - Pour contourner le serveur proxy, spécifier les paramètres de WinHTTP Proxy par votre serveur proxy et une liste de contournement, y compris la 192.168.213 ». \*« réseau utilisé par les services de nuage connecteur directions Skype pour Business Corpnet sous-réseau défini dans votre fichier CloudConnector.ini. Sinon, la connectivité de la gestion échouera et empêchera le déploiement et la récupération automatique de Cloud Connector. Voici un exemple de commande de configuration winhttp : netsh winhttp définie la liste de contournement proxy « 10.10.10.175:8080 » = «\*.local ; 1. \*; 172.20. \*; 192.168.218. \*'\<local\>».

  - Spécifiez les paramètres proxy par ordinateur au lieu de les spécifier par utilisateur. Téléchargements de nuage connecteur échoue dans le cas contraire. Vous pouvez spécifier des paramètres proxy par ordinateur en modifiant le registre ou via le paramètre de stratégie de groupe comme suit :

  - **Dans le Registre :** Paramètres HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet] DWORD : 00000000 ProxySettingsPerUser

  - **La stratégie de groupe :** Ordinateur\>modèles d’administration\>composants Windows\> Internet Explorer : paramètres de Proxy de rendre par ordinateur (et non par utilisateur)

- Système PBX/jonction ou SBC/passerelle qualifié (un minimum de deux passerelles est recommandé).

    Cloud Connector prend en charge les mêmes contrôleurs SBC (Session Border Controller) que ceux certifiés pour Skype Entreprise. Pour plus d'informations, reportez-vous à la rubrique relative à l'[infrastructure téléphonique pour Skype Entreprise](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

- Un compte d’administrateur de serveur local avec des autorisations pour installer et configurer Hyper-V sur les serveurs hôtes. Le compte doit disposer des autorisations d'administrateur sur le serveur local sur lequel Hyper V est installé et configuré.

- Lors du déploiement, vous devrez créer un compte d'administrateur de domaine avec les autorisations de création et de publication de la topologie dans le domaine Cloud Connector. 

- Enregistrements DNS externes définis dans le fichier CloudConnector.ini inclus dans le package d'installation :

  - Enregistrement DNS externe pour le service Edge d’accès du composant Edge ; par exemple, ap.\<nom de domaine\>. Vous aurez besoin d'un enregistrement par site PSTN. Cet enregistrement doit contenir les adresses IP de tous les Edges de ce site.

- Un client Office 365 avec toutes les enregistrements DNS et SRV créés.

    > [!IMPORTANT]
    > Lorsque vous intégrez votre client en nuage connecteur Edition, l’utilisation du suffixe de domaine par défaut,. onmicrosoft.com, comme un domaine SIP de votre organisation n'est pas pris en charge. > vous ne pouvez pas utiliser sip. \<Nom de domaine\> comme nom de votre connecteur de périphérie dans le nuage accès proxy interface car cet enregistrement DNS est utilisé par Office 365.

- Un certificat pour le serveur Edge externe obtenu auprès d'une autorité de certification publique (CA).

- Des règles de pare-feu visant à autoriser le trafic via les ports nécessaires ont été définies.

- Une connexion à Internet pour l'ordinateur hôte et les machines virtuelles. Nuage connecteur téléchargements certains logiciels à partir d’Internet ; Par conséquent, vous devez fournir de passerelle et les informations du serveur DNS afin que l’ordinateur hôte de nuage connecteur et les ordinateurs virtuels peuvent se connecter à Internet et télécharger le logiciel nécessaire.

- Un module PowerShell en client distant installé sur l'ordinateur hôte.

- Les informations d'identification d'administrateur de Skype Entreprise Office 365 pour exécuter PowerShell en client distant.

    > [!IMPORTANT]
    > L'authentification multi-facteur NE DOIT PAS être activée pour le compte administrateur.

> [!NOTE]
> Déploiement du connecteur sur le nuage est uniquement pris en charge sur la plateforme virtualisé Microsoft Hyper-V. Les autres plateformes, comme VMware et Amazon Web Services, ne le prennent pas en charge.

> [!NOTE]
> Les instructions de la configuration matérielle minimale pour exécuter le connecteur sur le nuage sont basée sur la capacité matérielle de base (cœurs, MHz, gigaoctets, etc.) avec une mémoire tampon pour s’adapter aux TROUBLES incorporelle performances de l’architecture de n’importe quel ordinateur. Microsoft a exécuté une vérification de la pire charge de cas sur du matériel disponible dans le commerce en s'appuyant sur une aide minimum. La qualité multimédia et les performances du système sont vérifiées. Partenaires de solution nuage connecteur officiels de Microsoft ont des implémentations matériel nuage connecteur spécifiques sur lesquels ils ont testés indépendamment des performances et attenant à la pertinence de leur matériel pour répondre aux besoins de charge et de la qualité.

> [!NOTE]
> Les appareils produits par AudioCodes et Sonus ont modifié le code et fonctionné sur une version de serveurs de Windows Server Standard. Ces appareils sont pris en charge.

## <a name="information-you-need-to-gather-before-deployment"></a>Informations que nécessaires pour recueillir avant le déploiement
<a name="BKMK_PlanDeployment"> </a>

Avant de commencer votre déploiement, vous devez déterminer sa taille, les domaines SIP pris en charge et les informations de configuration pour chacun des sites PSTN à déployer. Pour commencer, vous devez :

- Identifiez tous les domaines SIP pris en charge par ce déploiement basé sur les URI SIP utilisés dans votre société.

- déterminer le nombre de sites PSTN à déployer ;

- Vérifiez que vous disposez du matériel nécessaire pour prendre en charge les quatre ordinateurs virtuels que vous allez installer pour chaque version de connecteur dans le nuage.

Pour chaque site PSTN que vous prévoyez de déployer, vous devez :

- Créer des noms pour tous les composants de chaque solution nuage connecteur (voir [déterminer les paramètres de déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)).

- Définir des plages de ports (reportez-vous à la rubrique [Ports et protocoles](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)) ; 

- créer des enregistrements DNS externes pour le composant Edge (reportez-vous à la rubrique [Requirements for deployment](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)) ;

- déterminer les exigences en matière de certificats pour le composant Edge (reportez-vous à la rubrique [Certificate requirements](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)).

### <a name="ports-and-protocols"></a>Ports et protocoles
<a name="BKMB_Ports"> </a>

Lors de la définition des plages de ports multimédias, gardez les points suivants à l'esprit :

- Les clients utilisent toujours 50000 à 50019 la plage de ports pour le trafic multimédia — cette plage est prédéfinie dans Skype pour Business Online et ne peut pas être modifiée.

- Le composant de médiation utilise, par défaut, la plage de ports comprise entre 49 152 et 57 500 pour le trafic multimédia. Toutefois, l’établissement de la connexion via le pare-feu interne et, pour des raisons de sécurité, vous pouvez limiter cette plage de ports dans votre topologie. Vous devrez compter jusqu'à 4 ports par appel. Si vous souhaitez limiter le nombre de ports entre le composant de médiation et la passerelle PSTN, vous devrez également configurer la plage de ports correspondante sur la passerelle.

- Vous devez déployer dans le nuage connecteur dans un réseau de périmètre. Cela signifie que vous aurez deux pare-feu :

  - Le premier pare-feu est externe, entre Internet et votre réseau de périmètre.

  - Le deuxième pare-feu est interne entre le réseau de périmètre et le réseau interne.

    Vos clients peuvent se trouver sur Internet ou sur le réseau interne : 

  - Les clients sur Internet se connectent à votre réseau téléphonique public commuté (RTC) via le pare-feu externe, à travers le composant Edge.

  - Clients dans le réseau interne seront connecté via le pare-feu interne pour le composant de médiation dans le réseau de périmètre, qui se connectera le trafic vers la passerelle SBC ou PSTN.

    Vous devez donc ouvrir des ports dans les deux pare-feu. 

Les tableaux ci-dessous décrivent les ports et les plages de ports pour les pare-feu externe et interne.

Ce tableau indique les ports et les plages de ports permettant la communication entre les clients sur le réseau interne et le composant de médiation :

**Pare-feu interne**



|**Adresse IP source**|**Adresse IP de destination**|**Port source**|**Port de destination**|
|:-----|:-----|:-----|:-----|
|Composant de connecteur médiation dans le nuage  <br/> |Passerelle SBC/PSTN  <br/> |Indifférente  <br/> |TCP 5060\*\*  <br/> |
|Passerelle SBC/PSTN  <br/> |Composant de connecteur médiation dans le nuage  <br/> |Indifférente  <br/> |TCP 5068/TLS 5067  <br/> |
|Composant de connecteur médiation dans le nuage  <br/> |Passerelle SBC/PSTN  <br/> |UDP 49 152-57 500  <br/> |N’importe quel\*\*\*  <br/> |
|Passerelle SBC/PSTN  <br/> |Composant de connecteur médiation dans le nuage  <br/> |N’importe quel\*\*\*  <br/> |UDP 49 152-57 500  <br/> |
|Composant de connecteur médiation dans le nuage  <br/> |Clients internes  <br/> |TCP 49 152-57 500\*  <br/> |TCP 50 000 à 50 019  <br/> (Facultatif)  <br/> |
|Composant de connecteur médiation dans le nuage  <br/> |Clients internes  <br/> |UDP 49 152-57 500\*  <br/> |UDP 50 000 à 50 019  <br/> |
|Clients internes  <br/> |Composant de connecteur médiation dans le nuage  <br/> |TCP 50 000 à 50 019  <br/> |TCP 49 152-57 500\*  <br/> |
|Clients internes  <br/> |Composant de connecteur médiation dans le nuage  <br/> |UDP 50 000 à 50 019  <br/> |UDP 49 152-57 500\*  <br/> |

\*Il s’agit de la plage de ports par défaut sur le composant de médiation. Pour obtenir un flux d'appels optimal, quatre ports par appel sont nécessaires.

\*\*Ce port doit être configuré sur la passerelle SBC/RTC ; 5060 est un exemple. Vous pouvez configurer d’autres ports sur votre passerelle SBC/RTC.

\*\*\*Notez que vous pouvez également limiter la plage de ports sur votre contrôleur SBC/passerelle si autorisé par le fabricant SBC/passerelle.

Pour des raisons de sécurité, vous pouvez limiter la plage de ports pour le composant de médiation à l’aide de l’applet de commande [Set-CsMediationServer](https://docs.microsoft.com/powershell/module/skype/set-csmediationserver?view=skype-ps) .

Par exemple, la commande suivante limite le nombre de ports que le composant de médiation utilisera pour le trafic multimédia à 50 000-station 51 000 pour l’audio (entrée et sortie). Avec cette configuration, le composant de médiation pourra traiter 250 appels simultanés. Notez que vous souhaiterez peut-être également limiter cette plage sur la passerelle SBC/PSTN :

```
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

Pour récupérer le nom du composant de médiation et afficher les ports par défaut, vous pouvez utiliser l’applet de commande [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps) comme suit :

```
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

Le tableau suivant indique les ports et les plages de ports pour permettre la communication entre le composant nuage connecteur Edge pour le pare-feu externe. Ce tableau indique la configuration minimale recommandée.

Dans ce cas, tout le trafic multimédia à internet passera par le biais de la bordure en ligne comme suit : point de terminaison utilisateur--\>Online Edge--\>nuage connecteur Edge :

**Pare-feu externe - configuration minimale**



|**Adresse IP source**|**Adresse IP de destination**|**Port source**|**Port de destination**|
|:-----|:-----|:-----|:-----|
|Indifférente  <br/> |Interface externe du serveur Edge nuage connecteur  <br/> |Indifférente  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externe du serveur Edge nuage connecteur  <br/> |Indifférente   <br/> |Indifférente  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externe du serveur Edge nuage connecteur  <br/> |Indifférente   <br/> |Indifférente  <br/> |TCP 80  <br/> |
|Interface externe du serveur Edge nuage connecteur  <br/> |Indifférente   <br/> |Indifférente  <br/> |UDP 53  <br/> |
|Interface externe du serveur Edge nuage connecteur  <br/> |Indifférente   <br/> |Indifférente  <br/> |TCP 53  <br/> |
|Interface externe du serveur Edge nuage connecteur  <br/> |Indifférente  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Indifférente  <br/> |Interface externe du serveur Edge nuage connecteur  <br/> |TCP 50 000 à 59 999  <br/> |TCP 443  <br/> |
|Indifférente  <br/> |Interface externe du serveur Edge nuage connecteur  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Interface externe du serveur Edge nuage connecteur  <br/> |Indifférente  <br/> |TCP 50 000 à 59 999  <br/> |TCP 443  <br/> |

Le tableau suivant répertorie les ports et les plages de ports pour permettre la communication entre le composant nuage connecteur Edge pour le pare-feu externe. Ce tableau présente la solution recommandée.

Dans ce cas ensemble du trafic multimédia du point de terminaison dans internet peut être transmis directement au composant nuage connecteur Edge. Le chemin d’accès multimédia sera le Point de terminaison utilisateur -\> nuage connecteur Edge.

> [!NOTE]
> Cette solution ne fonctionne pas si le point de terminaison utilisateur est protégé par une fonction de conversion d'adresses réseau (NAT) symétrique.

**Pare-feu externe - configuration recommandée**


|**Adresse IP source**|**Adresse IP de destination**|**Port source**|**Port de destination**|
|:-----|:-----|:-----|:-----|
|Indifférente  <br/> |Interface externe du serveur Edge nuage connecteur  <br/> |Indifférente  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externe du serveur Edge nuage connecteur  <br/> |Indifférente   <br/> |Indifférente  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externe du serveur Edge nuage connecteur  <br/> |Indifférente   <br/> |Indifférente  <br/> |TCP 80  <br/> |
|Interface externe du serveur Edge nuage connecteur  <br/> |Indifférente   <br/> |Indifférente  <br/> |UDP 53  <br/> |
|Interface externe du serveur Edge nuage connecteur  <br/> |Indifférente   <br/> |Indifférente  <br/> |TCP 53  <br/> |
|Interface externe du serveur Edge nuage connecteur  <br/> |Indifférente  <br/> |TCP 50 000 à 59 999  <br/> |Indifférente  <br/> |
|Interface externe du serveur Edge nuage connecteur  <br/> |Indifférente  <br/> |UDP 3 478 ; UDP 50 000 à 59 999  <br/> |Indifférente   <br/> |
|Indifférente  <br/> |Interface externe du serveur Edge nuage connecteur  <br/> |Indifférente  <br/> |TCP 443 ; TCP 50 000 à 59 999  <br/> |
|Indifférente  <br/> |Interface externe du serveur Edge nuage connecteur  <br/> |Indifférente  <br/> |UDP 3478 ; UDP 50 000 à 59 999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>Conditions requises de l'hôte pour la connexion Internet
<a name="BKMB_Ports"> </a>

L’ordinateur hôte doit être en mesure d’atteindre des ressources externes pour installer, mettre à jour et gérer le nuage connecteur correctement. Le tableau suivant indique les destinations et ports nécessaires entre l'ordinateur hôte et les ressources externes.

|Direction  <br/> |Adresse IP source  <br/> |Adresse IP de destination  <br/> |Port source  <br/> |Port de destination  <br/> |Protocole  <br/> |Objectif  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sortant  <br/> |Hôte du connecteur cloud IP  <br/> |indifférente  <br/> |indifférente  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|Sortant  <br/> |Hôte du connecteur cloud IP  <br/> |indifférente  <br/> |indifférente  <br/> |80, 443  <br/> |TCP  <br/> |Liste de révocation de certificats (CRL)  <br/> |
|Sortant  <br/> |Hôte de Connectorr cloud IP  <br/> |indifférente  <br/> |indifférente  <br/> |80, 443  <br/> |TCP  <br/> |Mise à jour du connecteur de nuage  <br/> Skype Entreprise Online  <br/> Administrateur PowerShell  <br/> Windows Update  <br/> |

Si des règles plus restrictives sont nécessaires, consultez les URL suivantes sur liste blanche :

- [URL de liste de révocation de certificats ](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) sur [URL et plages d'adresses IP Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)

- Mise à jour Windows : [Comment faire pour configurer un pare-feu pour les mises à jour logicielles](https://technet.microsoft.com/en-us/library/bb693717.aspx)

- Skype pour Business Online Admin PowerShell : \*. online.lync.com

    Si une exclusion de proxy est nécessaire pour cette destination, vous devrez l'ajouter à la liste de contournement WinHTTP.

- Mise à jour de nuage connecteur : [Centre de téléchargement](https://aka.ms/CloudConnectorInstaller), [https://go.microsoft.com](https://go.microsoft.com), et[https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>Résolution des noms DNS pour le composant Edge
<a name="BKMB_Ports"> </a>

Le composant Edge doit résoudre les noms externes des services Office 365 et les noms d’autres composants de nuage connecteur internes.

Chaque composant Edge est un ordinateur à plusieurs connexions avec des interfaces interne et externe. Nuage connecteur déploie des serveurs DNS sur le composant de contrôleur de domaine au sein du réseau de périmètre. Vous pouvez pointer le serveur Edge pour le serveur DNS dans le périmètre pour toutes les résolutions de noms, mais vous devez activer le serveur DNS en nuage connecteur résoudre les noms externes en définissant une zone DNS contenant un ou plusieurs enregistrements DNS A pour les requêtes externes qui font référence nom recherches à d’autres serveurs DNS publics.

Dans le fichier .ini, si vous définissez comme domaine SIP le nom de domaine complet des passerelles du même domaine, la zone faisant autorité pour ce domaine SIP sera créée dans le serveur DNS au sein du périmètre. Si le serveur de périphérie pointe vers ce serveur DNS pour résoudre les noms, Edge résoudra jamais le _sipfederationtls. \<votre_domaine\> enregistrement DNS, qui est requis pour les flux d’appels. Dans ce cas, Microsoft recommande que vous fournissez un serveur DNS sur l’interface externe Edge pour résoudre les recherches de nom Internet, et chaque composant Edge doit utiliser un fichier hôte pour résoudre les autres noms de composant nuage connecteur sur des adresses IP.

> [!NOTE]
> Pour des raisons de sécurité, il est recommandé que vous ne pointez pas le serveur en nuage connecteur DNS pour les serveurs internes dans le domaine de production pour la résolution de nom.

### <a name="determine-deployment-parameters"></a>Définition des paramètres de déploiement
<a name="BKMK_SiteParams"> </a>

Vous devez d'abord définir les paramètres de déploiement communs suivants :


|**Option**|**Description**|**Remarques**|
|:-----|:-----|:-----|
|Domaines SIP  <br/> |Du URI SIP utilisés par des utilisateurs de la société. Fournit tous les domaines SIP pris en charge par ce déploiement. Vous pouvez disposer de plusieurs domaines SIP.  <br/> ||
|Nombre de sites PSTN  <br/> |Nombre de sites PSTN que vous allez déployer.  <br/> ||

Pour chaque site PSTN que vous envisagez de déployer, vous devrez rassembler les informations suivantes avant de commencer le déploiement. Vous devrez fournir ces informations lorsque vous mettez à jour le fichier CloudConnector.ini.

Lorsque vous configurez les informations de la passerelle, gardez à l'esprit les points suivants :

- Si vous disposez d'une seule passerelle, supprimez la section « deuxième passerelle » dans le fichier .ini. S'il y a plus de deux passerelles, suivez le format existant pour en ajouter de nouvelles.

- Assurez-vous que l'adresse IP et le port de la(des) passerelle(s) soit correcte.

- Pour permettre une haute disponibilité de la passerelle PSTN, conservez la passerelle secondaire ou ajoutez des passerelles.

(Facultatif) Pour limiter les numéros d'appels sortants, mettez à jour la valeur LocalRoute.



|**Paramètres de site**|**Description**|**Remarques**|
|:-----|:-----|:-----|
|Nom de domaine de la machine virtuelle  <br/> |Nom de domaine pour les composants internes du nuage connecteur. Ce domaine doit être différent du domaine de production. Il peut s'agir du même nom sur toutes les appliances de Cloud Connector.  <br/> Nom du fichier .ini : « VirtualMachineDomain »  <br/> |.domaine local recommandé.   <br/> |
|Nom de contrôleur de domaine dans le nuage connecteur  <br/> |Nom du contrôleur de domaine.   <br/> Nom du fichier .ini : « NomServeur »  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> |
|Nuage connecteur domaine contrôleur IP/masque de sous-réseau  <br/> |Adresse IP du contrôleur de domaine.   <br/> Nom du fichier .ini : « IP »  <br/> ||
|Noms de domaine complet des services en ligne O365  <br/> |Doit être la valeur par défaut dans la plupart des cas pour l’instance de O365 à l’échelle mondiale.  <br/> Nom du fichier .ini : « OnlineSipFederationFqdn »  <br/> ||
|SiteName  <br/> |Skype pour le nom du site Business ; par exemple, Seattle.  <br/> Nom du fichier .ini : « Nomsite »  <br/> Pour la version 1.4.1 et les suivantes, le nom du site doit être différent pour chaque site, et le nom doit correspondre au site PSTN, s'il existe, défini dans Office 365. Notez que les sites PSTN sont automatiquement créés au moment de l'inscription de la première appliance dans un site.  <br/> ||
|HardwareType  <br/> Version 1.4.1 et suivantes  <br/> |Type de matériel. La valeur par défaut est Normal. Vous pouvez également la définir sur Minimum.  <br/> ||
|Indicatif du pays  <br/> |Indicatif du pays/de la région pour la numérotation.  <br/> Nom du fichier .ini : « CountryCode »  <br/> ||
|Ville  <br/> |Ville (facultatif).  <br/> Nom du fichier .ini : « City »  <br/> ||
|État  <br/> |État (facultatif).  <br/> Nom du fichier .ini : « État »  <br/> ||
|Adresse IP des machines virtuelles de base  <br/> |L’adresse IP de l’ordinateur de base temporaire virtuel qui sera utilisé pour créer la VHDX pour tous les ordinateurs virtuels de nuage connecteur. Cette IP doit se trouver dans le même sous-réseau de réseau de périmètre d'entreprise défini dans l'étape suivante et requiert un accès Internet. Veillez à définir la passerelle par défaut et le DNS d'entreprise routable à Internet.  <br/> Nom du fichier .ini : « BaseVMIP »  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> Version 1.4.1 et suivantes  <br/> |L'adresse des services de mises à jour de serveur Windows (WSUS), un serveur intranet qui héberge les mises à jour depuis Microsoft Update.  <br/> Vous pouvez ne rien écrire si vous n'avez pas besoin de WSUS.   <br/> ||
|Masque de sous-réseau pour réseau interne  <br/> |Nuage connecteur configure un réseau IP pour les communications internes entre les composants du connecteur sur le nuage. Edge doit également être connecté à un autre sous-réseau qui permet la connexion à Internet.  <br/> Nom du fichier .ini : « CorpnetIPPrefixLength » sous « Paramètres pour un pool de réseau de l’ordinateur virtuel »  <br/> ||
|Masque de sous-réseau pour réseau externe   <br/> |Pour le réseau externe du composant Edge.  <br/> Nom du fichier .ini : « InternetIPPrefix » sous « Paramètres pour un pool de réseau de l’ordinateur virtuel »  <br/> ||
|Nom du commutateur pour réseau interne  <br/> |Nom de commutateur qui sera utilisé pour le réseau interne de nuage connecteur.  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nom du fichier .ini : « CorpnetSwitchName » sous « paramètres pour un pool de réseau de l’ordinateur virtuel  <br/> ||
|Nom du commutateur pour réseau externe  <br/> |Nom de commutateur qui sera utilisé pour le réseau dans le nuage connecteur externe.  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nom du fichier .ini : « InternetSwitchName » sous « paramètres pour un pool de réseau de l’ordinateur virtuel  <br/> ||
|Passerelle par défaut pour le réseau interne  <br/> |Cette passerelle doit fournir un accès à Internet (Internet requiert également la définition du serveur DNS) et sera configuré sur les interfaces internes des composants de connecteur dans le nuage.  <br/> Nom du fichier .ini : « CorpnetDefaultGateway » sous « paramètres pour un pool de réseau de l’ordinateur virtuel  <br/> ||
|Passerelle par défaut pour l'interface externe du composant Edge  <br/> |Sera configurée sur l'interface externe du composant Edge.  <br/> Nom du fichier .ini : « InternetDefaultGateway » sous « paramètres pour un pool de réseau de l’ordinateur virtuel  <br/> ||
|Serveur DNS pour réseau interne  <br/> |Sera configuré sur l'interface interne de la machine virtuelle temporaire. Doit fournir une résolution de noms pour les noms Internet. Si aucun serveur DNS n'est fourni, la connexion à Internet sera impossible et le déploiement ne s'achèvera pas.  <br/> Nom du fichier .ini : « CorpnetDNSIPAddress » sous « paramètres pour un pool de réseau de l’ordinateur virtuel  <br/> ||
|Serveur DNS pour interface externe du composant Edge  <br/> |Sera configuré sur l'interface externe du serveur Edge.  <br/> Nom du fichier .ini : « InternetDNSIPAddress » sous « paramètres pour un pool de réseau de l’ordinateur virtuel  <br/> ||
|Nom du commutateur de gestion  <br/> |Commutateur de gestion est un commutateur temporaire qui sera créé automatiquement, et qui sera utilisé pour la configuration du connecteur de nuage lors du déploiement. Il sera également déconnecté automatiquement après le déploiement. Il doit être un sous-réseau différent de celui de tout autre réseau utilisé dans le nuage connecteur.  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nom du fichier .ini : « ManagementSwitchName » sous « paramètres pour un pool de réseau de l’ordinateur virtuel  <br/> ||
|Masque de sous-réseau/adresse du sous-réseau de gestion  <br/> |Sous-réseau de gestion est un sous-réseau temporaire qui sera créé automatiquement, et qui sera utilisé pour la configuration du connecteur de nuage lors du déploiement. Il sera également déconnecté automatiquement après le déploiement. Il doit être un sous-réseau différent de celui de tout autre réseau utilisé dans le nuage connecteur.  <br/> Noms de fichier .ini : « ManagementIPPrefix » et « ManagementIPPrefixLength » sous « paramètres pour un pool de réseau de l’ordinateur virtuel  <br/> ||
|Ordinateur du magasin central de gestion (CMS)  <br/> |Nom de domaine complet unique utilisé pour le magasin central de gestion (CMS). Le nom du domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nom du fichier .ini : « Nomserveur » sous « paramètres de principal Service de gestion centralisée  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> (Nom du pool CMS = Nom du serveur)  <br/> |
|Adresse IP de la machine du magasin central de gestion  <br/> |Adresse IP de serveur CMS (interne dans le réseau de périmètre).  <br/> Nom de fichier INI : « IP » sous « paramètres de principal Service de gestion centralisée  <br/> ||
|Nom du partage de fichiers   <br/> |Nom de partage de fichier à créer sur le serveur CMS Skype pour les données métiers réplication (par exemple, CmsFileStore).  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nom du fichier .ini : « CmsFileStore » sous « paramètres de principal Service de gestion centralisée  <br/> ||
|Composant de médiation nom du Pool  <br/> |Nom du pool du composant de médiation. Entrez le nom NETBIOS uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nom du fichier .ini : « PoolName » sous « Paramètres pour un pool de serveurs de médiation »  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> |
|Nom de composant de médiation  <br/> |Nom du composant de médiation 1. Entrez le nom NETBIOS uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nom du fichier .ini : « Nomserveur » sous « Paramètres pour un pool de serveurs de médiation »  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> |
|Adresse IP de l’ordinateur du composant médiation  <br/> |IP Corpnet interne pour le composant de médiation (interne dans le réseau de périmètre).  <br/> Nom du fichier .ini : « IP » sous « Paramètres pour un pool de serveurs de médiation »  <br/> ||
|Nom interne du pool du serveur Edge  <br/> |Nom du pool du composant Edge. Entrez le nom NETBIOS uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nom du fichier .ini : « InternalPoolName » sous « Paramètres pour un pool de serveurs de périphérie »  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> |
|Nom interne du serveur Edge  <br/> |Nom du composant Edge. Entrez un nom Netbios uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.   <br/> Nom du fichier .ini : « InternalServerName » sous « Paramètres pour un pool de serveurs de périphérie »  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> |
|Adresse IP interne du serveur Edge   <br/> |Composant IP de périphérie du réseau périmètre interne de communiquer avec d’autres composants du nuage connecteur.  <br/> Nom du fichier .ini : « InternalServerIPs » sous « Paramètres pour un pool de serveurs de périphérie »  <br/> ||
|Nom externe du pool d'accès  <br/> |Nom du serveur Edge d'accès, par exemple, AP. Ce nom doit correspondre au nom indiqué pour le certificat SSL. Entrez un nom Netbios uniquement. Le nom de domaine SIP sera utilisé pour générer le nom de domaine complet. Un nom de pool externe serviront pour tous les composants Edge du pool. Un pool Edge d’accès est requis par site PSTN.  <br/> Nom du fichier .ini : « ExternalSIPPoolName » sous « Paramètres pour un pool de serveurs de périphérie »  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> « sip » est réservé et ne peut donc pas être utilisé comme nom.  <br/> Le nom de domaine complet généré doit correspondre au nom fourni pour le certificat SSL.   <br/> |
|Adresse IP externe du serveur Edge d’accès  <br/> |Composant IP du serveur Edge externe - l’adresse IP publique si aucune NAT n’est disponible, ou traduit IP (Veuillez préciser les deux adresses si mappé).  <br/> Nom du fichier .ini : « ExternalSIPIPs » sous « Paramètres pour un pool de serveurs de périphérie »  <br/> ||
|Nom du serveur relais multimédia  <br/> |Nom du serveur Edge du serveur relais multimédia audio/vidéo, par exemple, MR. Un seul nom de pool externe sera utilisé pour tous les composants Edge d'un pool. Un pool Edge le relais multimédia est requis par site PSTN.  <br/> Nom du fichier .ini : « ExternalMRFQDNPoolName » sous « Paramètres pour un pool de serveurs de périphérie »  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> |
|Adresse IP externe du bord de relais multimédia  <br/> |Actuellement une seule IP est pris en charge, il s’agit de la même adresse IP en tant que serveur Edge d’accès, public ou mappé IP (Veuillez préciser les deux adresses si mappé). Peut être la même adresse en tant que composant Edge externe IP du serveur Edge d’accès. Notez que si Edge derrière NAT, vous devez également spécifier la valeur pour le paramètre suivant.  <br/> Nom du fichier .ini : « ExternalMRIPs » sous « Paramètres pour un pool de serveurs de périphérie »  <br/> ||
|IP de médias relais périmètre externe (si Edge est derrière NAT)  <br/> |Si votre Edge est protégé par une traduction d'adresse réseau, vous devez également spécifier l'adresse publique du périphérique NAT.  <br/> Nom du fichier .ini : « ExternalMRPublicIPs » sous « Paramètres pour un pool de serveurs de périphérie »  <br/> ||
|Voix passerelle 1 marque et le modèle  <br/> |Indiquez la marque et le modèle de la passerelle SBC/vocale. Notez que vous pouvez connecter un périphérique ou une jonction SIP dans la liste des périphériques à [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP).  <br/> ||
|Vocale 2 Assurez-vous de passerelle et le modèle (copiez cette ligne si vous avez plus de 2 passerelles)  <br/> |Indiquez la marque et le modèle de la passerelle vocale. Notez que vous pouvez vous connecter un périphérique à partir de la liste des périphériques à [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP).  <br/> ||
|Nom de la passerelle 1 voix  <br/> |Utilisé pour générer le nom de domaine complet de la machine avec le domaine AD. Nécessaire si TLS est utilisé entre le composant de médiation et la passerelle vocale. Si vous ne souhaitez pas utiliser le nom de domaine complet, par exemple, TLS n’est pas requis ou passerelle vocale ne prennent en charge la connexion à l’aide du nom de domaine complet (IP uniquement), spécifiez.  <br/> ||
|Voix nom 2 de la passerelle (copie cette ligne si vous avez plus de 2 passerelles)  <br/> |Utilisé pour générer le nom de domaine complet de la machine avec le domaine AD. Nécessaire si TLS est utilisé entre le composant de médiation et la passerelle vocale. Si vous ne souhaitez pas utiliser le nom de domaine complet, par exemple, TLS n’est pas requis ou passerelle vocale ne prennent en charge la connexion à l’aide du nom de domaine complet (IP uniquement), spécifiez.  <br/> ||
|Adresse IP de passerelle 1 vocale  <br/> |Adresse IP de la passerelle vocale.  <br/> ||
|Vocale 2 Gateway IP Address (copie cette ligne si vous avez plus de 2 passerelles)  <br/> |Adresse IP de la passerelle vocale.  <br/> ||
|Voix passerelle 1 Port # (copie cette ligne si vous avez plus de 2 passerelles)  <br/> |Port écouté par la jonction SIP de la passerelle vocale, par exemple, 5 060.  <br/> ||
|Voix passerelle 2 ports #  <br/> |Port écouté par la jonction SIP de la passerelle vocale, par exemple, 5 060.  <br/> ||
|Protocole de passerelle 1 voix pour le trafic SIP  <br/> |TCP ou TLS.  <br/> ||
|Voix passerelle 2 protocole pour le trafic SIP (copie cette ligne si vous avez plus de 2 passerelles)  <br/> |TCP ou TLS.  <br/> ||
|Plage de ports multimédias externes pour le trafic à destination et en provenance du composant Edge  <br/> |Plage de ports TCP/UDP pour le trafic multimédia à destination et en provenance de l'interface externe du composant Edge. Doit toujours commencer à 50 000. Pour plus d’informations, reportez-vous à « Ports et protocoles ».  <br/> |50000 - 59 999  <br/> |
|Plage de communiquer dans le composant de médiation via le pare-feu interne de ports multimédias  <br/> |Plage de ports UDP que le composant de médiation utilisera pour communiquer avec les clients et passerelles (ports recommandation 4 par appel).  <br/> ||
|Plage pour communiquer dans Skype pour Business client via le pare-feu interne de ports multimédias  <br/> |Ne peut pas être modifiée en raison de la planification. Ports doivent être ouverts dans le pare-feu interne pour la communication entre Skype pour les clients d’entreprise au sein du réseau interne et le composant de médiation.  <br/> |50 000 à 50 019  <br/> |
|Mot de passe du certificat public  <br/> |Doit être indiqué dans le script.  <br/> ||
|Mot de passe administrateur en mode sans échec  <br/> Version 1.4.2 uniquement  <br/> |Mot de passe administrateur en mode sans échec pour le domaine Cloud Connector interne  <br/> ||
|Mot de passe administrateur de domaine dans le nuage connecteur  <br/> Version 1.4.2 uniquement  <br/> |Mot de passe pour le nuage connecteur administrateur de domaine (différent de votre domaine de production). Le nom d'utilisateur est Administrator. Vous ne pouvez pas le modifier.  <br/> ||
|Mot de passe administrateur des machines virtuelles  <br/> Version 1.4.2 uniquement  <br/> |Utilisé pour configurer le réseau de gestion lors du déploiement.  <br/> Le nom d'utilisateur est Administrator. Vous ne pouvez pas le modifier.   <br/> ||
|CABackupFile  <br/> Version 2.0 et ultérieures  <br/> |Utilisé pour enregistrer le Service de l’autorité de Certification à partir du serveur Active Directory dans un fichier lors du déploiement de plusieurs applications dans un site dans le nuage connecteur. Assurez-vous d'utiliser le même mot de passe pour toutes les appliances sur un même site Cloud Connector afin d'importer correctement le fichier de sauvegarde AC vers une nouvelle appliance.  <br/> ||
|CCEService  <br/> Version 2.0 et ultérieures  <br/> |Utilisé pour le service de gestion Cloud Connector ; nécessite l'accès à l'annuaire de site Cloud Connector. Assurez-vous d'utiliser le même mot de passe pour toutes les appliances sur un même site Cloud Connector.   <br/> ||
|Administrateur client Office 365  <br/> | Le compte est utilisé par Cloud Connector pour mettre à jour et gérer les paramètres du client pour Cloud Connector : <br/>  Version 2.0 et versions ultérieure : les informations d’identification pour un dédié Office 365 compte avec Skype de droits d’administrateur d’entreprise. <br/>  Version antérieure à 2.0 : informations d'identification d'un compte Office 365 dédié disposant des droits d'administrateur client global. <br/> ||
|Activer la prise en charge de REFER.  <br/> |Cela déterminera si la prise en charge de SIP REFER est activée ou désactivée sur la configuration de la jonction de votre IP/système PBX. La valeur par défaut est True. Si votre passerelle IP/PBX prend en charge REFER, veuillez laisser la valeur True. Si ce n’est pas le cas, cette valeur doit être remplacée par False. Si vous n'êtes pas certain que votre passerelle prend en charge REFER, veuillez vous reporter à la rubrique [IP-PBX et passerelles qualifiés](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).   <br/> ||
|EnableFastFailoverTimer  <br/> Version 2.0 et ultérieures  <br/> |Avec la valeur par défaut « True », si les appels sortants sont sans réponse par la passerelle dans les 10 secondes qu’ils sont acheminés vers la passerelle suivante disponible ; s’il n’existe aucune jonctions supplémentaires l’appel est supprimé automatiquement.  <br/> Cependant, dans une organisation dont les réseaux et les réponses de la passerelle sont lents, ou lorsque la procédure d'établissement d'appel dépasse les 10 secondes, cela peut entraîner l'abandon inutile des appels.  <br/> Lorsque des appels sont passés vers certains pays, par exemple les Émirats arabes unis ou l'Afghanistan, la procédure d'établissement d'appel peut prendre plus de 10 secondes. Si vous rencontrez ces problèmes, vous devrez modifier la valeur en « False ». N'oubliez pas de modifier le paramètre correspondant sur le SBC ou la passerelle connecté(e).  <br/> Les valeurs peuvent être « True » ou « False ». La valeur par défaut est « True ».  <br/> ||
|ForwardCallHistory  <br/> Version 2.0 et ultérieures  <br/> | Ce paramètre est utilisé pour les en-têtes SIP utilisés pour signaler l'appelant initial dans des scénarios de sonnerie simultanée et de transfert d'appel. Définir le paramètre sur « True » entraîne l'activation de deux en-têtes SIP :<br/>  History-Info <br/>  Referred-By <br/>  L’en-tête de l’historique des Info est utilisé pour le ciblage de nouveau les demandes SIP et « minutieuses un mécanisme standard pour capturer les informations de l’historique de la demande pour activer un large éventail de services pour les réseaux et les utilisateurs finaux » ([RFC 4244 - point 1.1](http://www.ietf.org/rfc/rfc4244.txt)). En ce qui concerne les interfaces de jonction de Cloud Connector, elles sont utilisées dans des scénarios de sonnerie simultanée et de transfert d'appel.  <br/>  Les valeurs peuvent être « True » ou « False ». La valeur par défaut est « False ».<br/> ||
|Transfert PAI  <br/> Version 2.0 et ultérieures  <br/> |PAI est une extension privée de SIP qui permet aux serveurs SIP de déclarer l'identité des utilisateurs authentifiés. Pour le fournisseur de jonction SIP, PAI peut être utilisé à des fins de facturation, dans les cas où les en-têtes History-Info et Referred-By sont absents. Lorsque le transfert P-Asserted-Identity est activé dans la configuration, le serveur de médiation transmet les en-têtes PAI avec SIP &amp; Tel URI nuage connecteur sur la jonction SIP. Le serveur de médiation transmet les en-têtes PAI avec tel URI &amp; reçus uniquement sur la jonction SIP vers le nuage connecteur les numéros E.164. Le serveur de médiation transférera également tout en-tête Privacy reçu dans l'une des directions. Si le SIP demande envoyés par le serveur de médiation inclut un en-tête de confidentialité de l’écran - « confidentialité : id » en association avec l’en-tête PAI, puis l’identité déclarée doit rester privée en dehors du domaine d’approbation de réseau.  <br/> Les valeurs peuvent être « True » ou « False ». La valeur par défaut est « False ».  <br/> ||

### <a name="certificate-requirements"></a>Exigences en matière de certificats
<a name="BKMK_Certs"> </a>

Chaque composant Edge nécessite un certificat délivré par une autorité de certification publique. Les certificats doivent disposer d'une clé privée exportable pour pouvoir être copiés d'un composant Edge à l'autre. Pour respecter ces exigences, vous devrez choisir entre les options ci-après et indiquer le nom de sujet (SN) et un autre nom de sujet (SAN) pour le certificat :

 **Si vous disposez d'un domaine SIP unique :**

- **Option 1.** Le nom de sujet doit contenir le nom du pool affecté aux composants Edge. Notez que le nom du sujet ne peut pas être sip.sipdomain.com car ce nom est réservé pour le Skype en ligne pour le composant de bord d’entreprise. L'autre nom de sujet doit contenir sip.sipdomain.com et le nom du pool Edge d'accès :

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **Option 2.** Si vous souhaitez utiliser un certificat générique unique sur tous les serveurs de pool Edge vous déployez, puis vous pouvez utiliser une entrée de SAN générique de \*. sipdomain.com plutôt que le nom du pool Edge dans le certificat. Le nom de sujet peut être le nom d'un des pools Edge d'accès que vous avez déployés :

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> Vous ne devez pas créer une entrée DNS externe pour sip. \<sipdomain\>.com, car ce nom appartient au déploiement d’Office 365.

> [!NOTE]
> Si vous souhaitez utiliser un certificat unique pour tous les pools Edge déployés dans votre organisation et ne pouvez pas utiliser un certificat générique comme défini dans l'option 2, vous devrez alors inclure le nom de domaine complet pour tous les pools Edge déployés dans le nom SAN dans le certificat. 

 **Si vous disposez de plusieurs domaines SIP :**

Vous devez ajouter sip.sipdomain.com pour chaque domaine SIP, ainsi que le nom des pools Edge d'accès par domaine (il peut s'agir d'un pool physique avec des noms différents). Vous trouverez ci-dessous un exemple d'entrées SN et SAN dans un scénario comportant plusieurs domaines SIP :

- **Option 1.** Le nom du sujet doit contenir le nom du pool que vous avez affecté pour les composants Edge. Notez que le nom du sujet ne peut pas être sip.sipdomain.com car ce nom est réservé pour le Skype en ligne pour le composant de bord d’entreprise. L'autre nom de sujet doit contenir sip.sipdomain.com et le nom du pool Edge d'accès :

  ```
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>Option 2.</strong> Si vous souhaitez utiliser un certificat générique unique sur tous les serveurs de pool Edge vous déployez, puis vous pouvez utiliser une entrée de SAN générique de \*. sipdomain.com plutôt que le nom du pool Edge dans le certificat. Le nom de sujet peut être le nom d'un des pools Edge d'accès que vous avez déployés :

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> Vous ne devez pas créer une entrée DNS externe pour sip. \<sipdomain\>.com, car ce nom appartient au déploiement d’Office 365.

Dans le cadre d'un déploiement, vous pouvez utiliser le tableau suivant :

|**Option**|**Description**|**Remarques**|
|:-----|:-----|:-----|
|Quelle option allez-vous utiliser pour votre déploiement ?  <br/> |Option 1 ou 2  <br/> ||
|SN  <br/> |Indique le nom de sujet du certificat  <br/> ||
|SAN  <br/> |Indique l'autre nom de sujet du certificat  <br/> ||

Si vous utilisez TLS entre la passerelle et le serveur de médiation, vous devrez obtenir le certificat racine ou la chaîne de certificats complète pour le certificat assigné à la passerelle.

## <a name="dial-plan-considerations"></a>Aspects relatifs au plan de numérotation
<a name="BKMK_DailPlan"> </a>

Cloud Connector requiert l'utilisation d'un plan de numérotation en ligne. Pour plus d’informations sur la façon de configurer un plan de numérotation en ligne, voir [Quels sont les plans de numérotation ?](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>Considérations relatives à la haute disponibilité
<a name="BKMK_HA"> </a>

Lorsque vous déployez le nuage connecteur Edition pour une haute disponibilité, vous déployez au moins deux appliances qui agissent en tant que sauvegarde les uns aux autres. Chaque appliance se compose de quatre composants : contrôleur de périphérie, médiation, magasin Central de gestion (CMS) et du domaine.

En règle générale, si un composant dans un matériel tombe en panne, nuage connecteur Edition peut continuer à traiter les appels, mais vous devez prendre en compte les éléments suivants :

- **Mediation, CMS et les considérations relatives au composant du contrôleur de domaine**

    Supposons que le composant du contrôleur de domaine ou du magasin central de gestion d'une appliance ne fonctionne pas. L'appliance peut toujours traiter les appels entrants et sortants, mais si vous relancez un composant de médiation lorsque le composant du contrôleur de domaine ou du magasin central de gestion est inaccessible, la médiation ne fonctionnera pas. Vous ferez face à la même situation si vous relancez le composant du magasin central de gestion lorsque le contrôleur de domaine est en panne.

    **Recommandation :** Avant de redémarrer des composants, vérifiez la disponibilité d’autres composants de la solution.

- **Considérations relatives au composant Edge**

    Si le composant Edge d'une appliance n'est pas disponible, le comportement des appels entrants et sortants changera, de la façon suivante :

  - **Appel sortant**— un appel à partir de l’utilisateur dans Internet à un réseau RTC.

    Le mécanisme de distribution d'appels dans le cloud identifiera le fait que l'un des composants Edge est hors service et acheminera tous les appels vers une autre appliance, afin que l'appel sortant aboutisse.

  - **Appels entrants**, un appel à partir du réseau PSTN à un utilisateur qui est dans un réseau local ou sur Internet.

     Si le composant Edge de l'appliance qui a reçu l'appel ne fonctionne pas, les appels entrants dans cette appliance ne fonctionneront pas, car le composant de médiation ne peut pas rediriger l'appel vers le composant Edge dans l'autre appliance.

    **Recommandation :** Disposez d’un système de surveillance en place. Après avoir identifié une défaillance du composant Edge, arrêtez tous les composants de l’application dans laquelle le composant Edge n’est pas disponible.

## <a name="cloud-connector-media-flow"></a>Trafic multimédia de Cloud Connector
<a name="BKMK_MediaFlow"> </a>

Les schémas suivants détaillent le flux d’un appel entrant et sortant via le nuage connecteur Edition. Ces informations sont utiles pour comprendre comment la connexion est établie.

Sur la première illustration, un utilisateur interne passe un appel sortant, comme suit :

1. Dave, un utilisateur hébergé en ligne, mais qui se trouve actuellement sur le réseau interne, appelle un utilisateur RTC externe.

2. Itinéraires le trafic SIP Skype pour Business Online.

3. Skype pour Business Online effectue une recherche inversée de numéro du nombre. La recherche inversée de numéro échoue parce que ce numéro n’appartient pas à tout le monde dans la Skype pour l’organisation de l’entreprise.

4. L'appel est acheminé vers le composant Edge (trafic SIP et multimédia par le biais du composant Online Edge dans un premier temps, puis le trafic multimédia vers le composant de médiation par le biais du pare-feu interne).

5. Si l'itinéraire existe, le composant Edge relaie le trafic vers le composant de médiation dans le réseau de périmètre.

6. Le composant de médiation envoie le trafic vers la passerelle PSTN.

![Flux de média sortant pour Cloud Connector](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

Sur l'illustration ci-dessous, un utilisateur interne reçoit un appel entrant comme suit :

1. La passerelle PSTN reçoit un appel pour l'utilisateur Dave, qui est hébergé en ligne, mais se trouve actuellement sur le réseau interne.

2. Le trafic SIP est acheminé vers le composant de médiation.

3. Le composant de médiation envoie le trafic SIP au composant Edge, puis il accède à Skype pour Business Online.

4. Skype pour Business Online effectue une recherche inversée de numéro du nombre et détecte qu’il s’agit de l’utilisateur Dave.

5. La signalisation SIP est envoyée vers tous les points de présence de Dave.

6. Le trafic multimédia est établi entre la passerelle et le composant de médiation et entre le composant de médiation et le point de terminaison.

![Flux de média entrant pour Cloud Connector](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>Analyse et résolution des problèmes
<a name="BKMK_Monitor"> </a>

Le mécanisme d'analyse et de résolution des problèmes est installé automatiquement avec chaque appliance Cloud Connector. Le mécanisme détecte les événements suivants :

- Un ou plusieurs ordinateurs d'une appliance Cloud Connector ne sont pas connectés à un commutateur virtuel interne ou internet.

- Un ou plusieurs ordinateurs d'une appliance Cloud Connector sont en état Enregistré ou Arrêté.

- Les services ne sont pas exécutés.

  Si un des événements suivants est détecté, l’appliance nuage connecteur entière est déchargée et marqué en mode hors connexion pour empêcher la tentative d’établir des appels à un matériel ne fonctionne pas correctement. Les fonctionnalités de récupération automatique de Cloud Connector restaureront ensuite les services et marqueront l'appliance comme étant en ligne. Si la récupération automatique échoue pour une raison quelconque, reportez-vous à [Troubleshoot your Cloud Connector deployment](troubleshoot-your-cloud-connector-deployment.md).

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

Cloud Connector 2.1 et les versions ultérieures prennent en charge la surveillance de Cloud Connector avec Operations Management Suite (OMS). Pour plus d’informations, reportez-vous à la rubrique [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md).

## <a name="for-more-information"></a>Pour plus d'informations
<a name="BKMK_MoreInfo"> </a>

Pour plus d’informations, voir les articles suivants :

- [Solutions de téléphonie Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)

- [Configuration et gestion de Skype Entreprise, version Cloud Connector](configure-skype-for-business-cloud-connector-edition.md)

- [Planification de la déviation du trafic multimédia dans la version Cloud Connector](plan-for-media-bypass-in-cloud-connector-edition.md)

- [Déployer le contournement de média dans le nuage connecteur Edition](deploy-media-bypass-in-cloud-connector.md)


