---
title: Planification pour Skype Entreprise, version Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
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
ms.assetid: 6ce0e580-8c4a-45de-a54f-e39e438335d6
description: Obtenez des informations sur la version Cloud Connector de Skype Entreprise, un ensemble de machines virtuelles (VM) qui met en œuvre une connectivité PSTN locale avec un système téléphonique d'Office 365 (Cloud PBX).
ms.openlocfilehash: 1ef79cc9d50e21dc8b3376901638cd4f34e03f62
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287012"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Planification pour Skype Entreprise, version Cloud Connector

Obtenez des informations sur la version Cloud Connector de Skype Entreprise, un ensemble de machines virtuelles (VM) qui met en œuvre une connectivité PSTN locale avec un système téléphonique d'Office 365 (Cloud PBX).

L’édition Cloud Connector peut être la solution adaptée à votre organisation si vous n’avez pas encore de déploiement Lync Server ou Skype entreprise Server existant. Si vous étudiez toujours quel système téléphonique dans la solution 365 Office est approprié pour votre entreprise, voir [solutions de téléphonie Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions).

Ce document décrit les exigences en matière de édition Cloud Connector et les topologies prises en charge, et vous aide à planifier le déploiement de votre version Cloud Connector. Avant de configurer votre environnement Cloud Connector, veillez à lire ce sujet. Lorsque vous êtes prêt à déployer et configurer le Cloud Connector Edition, reportez-vous à la rubrique [configurer et gérer Skype entreprise version Cloud Connector](configure-skype-for-business-cloud-connector-edition.md).

La version 2,1 du Cloud Connector est désormais disponible. Si vous n'avez pas encore effectué la mise à niveau vers la version 2.1, reportez-vous à la rubrique [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md). Vous pouvez trouver le fichier d’installation [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)sur.

> [!NOTE]
> Microsoft prend en charge la version précédente de l’édition Cloud Connector pour 60 jours après la publication d’une nouvelle version. Microsoft prend en charge la version 2.0.1 pendant 60 jours après la sortie de la version 2.1 pour vous laisser le temps de la mettre à niveau. Toutes les versions antérieures à 2.0.1 ne sont plus prises en charge.

La version Cloud Connector est une offre hybride composée d’un ensemble d’ordinateurs virtuels empaquetés qui implémentent une connectivité PSTN locale avec le système téléphonique dans Office 365. Le déploiement d’une topologie de serveur Skype entreprise minimale dans un environnement virtualisé permet aux utilisateurs de votre organisation qui résident dans le Cloud de recevoir des services PBX du Cloud Microsoft, mais la connectivité RTC est assurée par le biais de la voix locale existante. infrastructure.

![Diagramme de topologie montrant Cloud PBX Gateway reliant Cloud PBX à un déploiement local de Skype Entreprise.](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

Comme Cloud Connector vous permert d'intégrer le système téléphonique dans les services d'Office 365 à votre environnement téléphonique actuel (par exemple PBX, des appareils analogiques et des centres d'appels), vous pouvez implémenter une migration progressive vers le système téléphonique d'Office 365.

Par exemple, imaginons que votre entreprise possède un centre d'appels sophistiqué avec des fonctionnalités spécifiques que le système téléphonique d'Office 365 ne fournit pas. Vous pouvez choisir de garder la solution existante pour les utilisateurs du centre d'appels, mais de déplacer les autres utilisateurs vers le système téléphonique d'Office 365.

Cloud Connector se chargera du routage entre les utilisateurs hébergés localement et ceux hébergés en ligne, et vous pouvez choisir d'utiliser votre propre fournisseur PSTN avec le système téléphonique d'Office 365.

Prenez en compte les points suivants lorsque vous planifiez le déploiement de votre édition Cloud Connector:

- Pour utiliser le Cloud Connector pour tirer parti des solutions vocales Cloud, vous devez vous inscrire à un client Office 365 qui inclut un système téléphonique dans Office 365. Si vous n’avez pas encore de client Office 365, vous pouvez découvrir comment vous inscrire ici: [Office 365 pour les entreprises](https://products.office.com/en-us/business/office). Notez que vous devez vous inscrire à un plan incluant Skype entreprise online.

- Pour enregistrer les appareils Cloud Connector avec le service Skype entreprise Online et pour exécuter diverses cmdlets, le Cloud Connector 2,0 et les versions ultérieures requièrent un compte Office 365 dédié avec les droits d’administrateur de clients Skype entreprise. Les versions de Cloud Connector antérieures à 2.0 requièrent un compte Office 365 dédié disposant des droits d'administrateur client global.

- Le Cloud Connector ne nécessite pas de déploiement complet de Skype entreprise Server sur site.

    Pour le moment, le Cloud Connector ne peut pas être coexistence avec des serveurs locaux Lync ou Skype entreprise. Si vous voulez déplacer des utilisateurs existants de Lync ou Skype entreprise vers Office 365 et continuer à fournir de la téléphonie locale à vos utilisateurs, envisagez un système téléphonique dans Office 365 avec une connectivité locale utilisant un déploiement Skype entreprise Server existant. Pour plus d’informations, reportez-vous à [la rubrique planification de votre système téléphonique dans la solution office 365 (PBX Cloud)](plan-your-phone-system-cloud-pbx-solution.md) et [planification du système téléphonique dans Office 365 avec la connectivité PSTN locale dans Skype entreprise Server](plan-phone-system-with-on-premises-pstn-connectivity.md).

- Si vous avez effectué un déploiement Skype entreprise ou Lync Server antérieur et que vous avez étendu le schéma, vous n’avez pas besoin de nettoyer le schéma pour le déploiement Cloud Connector, tant que vous avez supprimé tous les composants Skype entreprise ou Lync Server de votre environnement.

- Vos utilisateurs sont hébergés en ligne.

- Si votre organisation a configuré la synchronisation Active Directory (DirSync), tous les comptes des utilisateurs planifiés pour la voix hybride doivent être créés en premier lieu localement, puis synchronisés vers le cloud.

- Vous pouvez conserver votre opérateur RTC actuel, si nécessaire.

- Si vous voulez fournir des conférences rendez-vous aux utilisateurs hébergés sur le Cloud Connector, vous pouvez acheter une licence de conférence PSTN ou payer au fur et à mesure de l’audioconférence auprès de Microsoft.

- Le contrat de licence d’audioconférence (ou la fonction payer au fur et à mesure) est également requis pour la réaffectation des appels. Si un utilisateur de Skype entreprise reçoit un appel de la part d’un utilisateur RTC externe et veut ajouter un autre participant à cet appel (en transférant l’appel vers une conférence), le rapport sera exécuté par le biais du service Microsoft audio Conferencing.

- Cloud Connector 2.0 et les version ultérieures prennent désormais en charge la déviation du trafic. Bypass Media permet à un client d’envoyer des contenus multimédias directement sur le tronçon de réseau téléphonique commuté (PSTN), une passerelle ou un contrôleur de bordure de session (SBC), et d’éliminer le composant Cloud Connector édition sur le chemin multimédia. Pour plus d’informations, reportez-vous à la section [planification de la dérivation multimédia dans la version Cloud Connector](plan-for-media-bypass-in-cloud-connector-edition.md).

- Cloud Connector 2.1 et les versions ultérieures prennent en charge la surveillance de Cloud Connector avec Operations Management Suite (OMS). Pour plus d’informations, reportez-vous à la rubrique [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md).

- Le Cloud Connector est disponible dans tous les pays dans lesquels Office 365 entreprise E5 est disponible.

Cette rubrique contient les sections suivantes :

- [Composants de la version Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [Topologies de la version Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [Configuration requise pour le déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [Informations dont vous avez besoin pour rassembler le déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [Aspects relatifs au plan de numérotation](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [Considérations relatives à la haute disponibilité](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [Trafic multimédia de Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [Analyse et résolution des problèmes](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [Pour plus d'informations](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>Composants de la version Cloud Connector
<a name="BKMK_Components"> </a>

Avec la version Cloud Connector, vous déployez un ensemble de machines virtuelles empaquetées qui contiennent une topologie serveur minimum Skype entreprise, composée d’un composant de périphérie, d’un composant de médiation et d’un rôle de magasin de gestion central (CMS). Vous devez également installer un contrôleur de domaine requis pour le fonctionnement interne du connecteur Cloud. Ces services sont configurés pour un déploiement hybride avec votre client 365 Office qui inclut les services Skype entreprise online.

![Composants de la version Cloud Connector](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

Les composants Cloud Connector fournissent les fonctionnalités suivantes:

- **Composante latérale** -la communication entre la topologie locale et les services en ligne traverse le composant Edge, qui inclut les composants suivants:

  - **Accès Edge** : fournit le routage SIP entre le déploiement local et Skype entreprise online.

  - **Relais multimédia** : fournit un routage de média entre le composant de médiation et d’autres points de terminaison multimédia.

  - **Authentification par relais multimédia/MRAS** : génère des jetons pour accéder à l’accès au relais multimédia.

- **Routage sortant** -fournit l’équilibrage de charge du trafic vocal entre les passerelles ou SBCS connecté à un appareil de connecteur Cloud. Les appels seront répartis uniformément entre toutes les passerelles ou SBCs connectées à l’appareil Cloud Connector.

    Fournit un routage vers les passerelles en fonction des stratégies. Seules les politiques mondiales dépendant des numéros PSTN de destination (trafic sortant) sont prises en charge.

- **Rôle du magasin de gestion centralisée (CMS)** inclut le magasin de configuration pour les composants topologiques, y compris le transfert de fichier CMS.

- **Réplica de la Banque centrale de gestion (CMS)** : synchronise les informations de configuration du MCG global sur le serveur de rôles CMS.

- **Contrôleur de domaine** : services de domaine Active Directory du Cloud Connector pour stocker tous les paramètres globaux et groupes nécessaires au déploiement des composants Cloud Connector. Une seule forêt sera créée pour chaque appareil de connecteur Cloud. Le contrôleur de domaine ne doit pas avoir de connexions avec l’annuaire Active Directory de production. Les services Active Directory incluent:

  - Services de domaine Active Directory

  - Services de certificats Active Directory permettant d'émettre des certificats internes

- **Composant de médiation** -implémente le protocole SIP et Media Gateway Mapping entre les passerelles RTC et Skype entreprise. Inclut un réplica CMS qui synchronise la configuration à partir de la base de données CMS globale.

## <a name="cloud-connector-edition-topologies"></a>Topologies de la version Cloud Connector
<a name="BKMK_Topologies"> </a>

Dans le cadre de cet article, nous les appellerons « sites PSTN ». Un site RTC est une combinaison d’appareils de connexion Cloud, déployée au même emplacement et avec des passerelles RTC communes connectées. Les sites PSTN permettent d'effectuer les opérations suivantes :

- Fournissez une connectivité aux passerelles les plus proches de vos utilisateurs.

- Autorisez l’évolutivité en déployant plusieurs dispositifs Cloud Connector au sein d’un ou plusieurs sites RTC.

- Autorisez la haute disponibilité en déployant plusieurs dispositifs Cloud Connector au sein d’un seul site PSTN.

Cette rubrique présente les sites PSTN. Pour plus d'informations sur la planification de vos sites PSTN, reportez-vous à la rubrique [Plan for Cloud Connector Edition PSTN sites](plan-for-cloud-connector-edition-pstn-sites.md).

Vous pouvez déployer les topologies de connecteur Cloud suivantes:

- Une seule application Cloud Connector Edition par site PSTN. Cette topologie n'est recommandée que pour les évaluations car elle ne fournit pas de haute disponibilité.

- Plusieurs applications Cloud Connector pour un site PSTN pour une disponibilité élevée.

- Plusieurs sites RTC dotés de plusieurs Appliances Cloud Connector pour une évolutivité accrue. Vous pouvez déployer jusqu'à 200 sites.

Lors de la planification de votre topologie, tenez compte des points suivants :

- Avec le Cloud Connector 2,0 et les versions ultérieures, un site PSTN peut comporter jusqu’à 16 appareils de connexion Cloud. Les versions antérieures prennent en charge jusqu'à 4 appliances par site.

- Il existe deux types de configuration matérielle testés avec Cloud Connector:

  - La plus grande version est capable de traiter un large volume d'appels simultanés et est prise en charge dans tous les types d'environnements de production.

  - La version réduite est destinée à une exécution sur du matériel bas de gamme et peut être utilisée pour des évaluations ou pour des sites traitant peu d'appels. Si vous déployez la version réduite de Cloud Connector, vous devez continuer à tenir compte de la configuration matérielle requise pour la production (par exemple, deux sources d'alimentation).

- Si vous avez le Cloud Connector version 2,0 ou une version ultérieure et que vous déployez la configuration maximale de 16 appareils (avec un matériel important), votre site PSTN peut gérer jusqu’à 8 000 appels simultanés. Si vous déployez la version réduite, la limite est de 800.

    Vous devez également dédier quelques appliances à la haute disponibilité. Il est recommandé de dédier au moins une appliance à la haute disponibilité.

  - Avec la version 2, si vous déployez une configuration de 15 + 1, votre site PSTN peut gérer jusqu’à 7 500 appels simultanés.

  - Si vous disposez d'une version antérieure et que vous déployez la configuration maximum, 3 + 1 (avec du matériel plus conséquent), votre site PSTN peut gérer jusqu'à 1 500 appels simultanés. Si vous déployez la version réduite, la limite est de 150.

-  Si vous avez besoin de davantage d'appels par site PSTN, vous pouvez développer votre installation en déployant des sites PSTN supplémentaires au même emplacement.

> [!NOTE]
> Sauf indication contraire, les diagrammes et exemples ci-dessous supposent l’utilisation de la version plus grande de Cloud Connector.

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>Appliance unique Cloud Connector dans un site PSTN unique

Le diagramme suivant illustre une seule Appliance Cloud Connector sur un seul site PSTN. Notez que le connecteur Cloud est composé de quatre ordinateurs virtuels installés sur un ordinateur hôte physique qui se trouve au sein d’un réseau de périmètre à des fins de sécurité.

![Cloud Connector avec un site RTC](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>Plusieurs appliances Cloud Connector dans un site PSTN unique

 Pour des raisons d’évolutivité et de haute disponibilité, vous pouvez choisir d’avoir plusieurs éditions Cloud Connector au sein d’un même site RTC, comme illustré dans le schéma suivant. Dans ce cas, tenez compte des points suivants :

- Les appels sont distribués dans un ordre aléatoire entre les instances Cloud Connector d'un pool.

- Pour des raisons de planification des capacités, vous devez envisager la possibilité de gérer la charge si une ou plusieurs appliances Cloud Connector passent en mode hors connexion, en fonction des calculs suivants :

  - **Cases N+1.** Dans le cas d’une version plus grande de Cloud Connector, les zones\*N + 1 prennent en charge les appels simultanés 500 N avec une disponibilité 99,8%.

    Pour la version plus petite du Cloud Connector, les zones N + 1\*prennent en charge les appels simultanés 50 N avec une disponibilité 99,8%.

  - **Cases N+2.** Dans le cas d’une version plus grande de Cloud Connector, les zones\*N + 2 prennent en charge les appels simultanés 500 N avec une disponibilité 99,9%.

    Pour la version plus petite du Cloud Connector, les zones N + 2\*prennent en charge les appels simultanés 50 N avec une disponibilité 99,9%.

![Deux connecteurs de cloud dans 1 site RTC](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>Plusieurs sites PSTN avec une ou plusieurs instances Cloud Connector par site

Vous pouvez également opter pour la création de plusieurs sites PSTN avec une ou plusieurs versions de Cloud Connector sur chaque site. Si votre site PSTN atteint la limite d'appels simultanés, vous pouvez ajouter un autre site PSTN pour gérer la charge.

Une configuration à plusieurs sites PSTN permet également de fournir une connectivité aux passerelles les plus proches de vos utilisateurs. Supposez, par exemple, que vous utilisiez des passerelles PSTN à Seattle et Amsterdam. Vous pouvez déployer deux sites PSTN, l'un à Seattle, l'autre à Amsterdam, et affecter des utilisateurs de sorte qu'ils utilisent le site PSTN le plus proche. Les utilisateurs de Seattle seront acheminés vers le site PSTN et les passerelles de Seattle, tandis que les utilisateurs d'Amsterdam seront acheminés vers le site PSTN et les passerelles d'Amsterdam :

![Version Cloud Connector dans 2 sites RTC](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>Configuration requise pour le déploiement
<a name="BKMK_Requirements"> </a>

Avant de déployer l’édition Cloud Connector, assurez-vous d’avoir les éléments suivants pour votre environnement:

- **Pour l’ordinateur hôte-** Les VM sur le Cloud Connector doivent être déployées sur un matériel dédié exécutant Windows Server 2012 R2 Datacenter Edition (English) avec le rôle Hyper-V activé.

    Pour la version 2.0 et les suivantes, la carte réseau de l'ordinateur hôte attachée au commutateur de réseau entreprise de Skype Entreprise doit disposer d'une adresse IP configurée dans le même sous-réseau que les ordinateurs du réseau d'entreprise de Cloud Connector. 

- Pour les versions 2,1 et ultérieures, l’appareil hôte doit disposer de .NET Framework 4.6.1 ou version ultérieure.

- **Pour les machines virtuelles-** Image Windows Server 2012 R2 ISO (. ISO). L’ISO sera convertie en VHD pour les machines virtuelles exécutant Skype entreprise version Cloud Connector.

- Le matériel nécessaire pour prendre en charge l’installation des 4 VM pour chaque édition Cloud Connector dans votre déploiement. Les configurations ci-dessous sont recommandées :

  - processeur double cœur de 64 bits, sixième cœur (12 cœurs), 2,50 gigahertz (GHz) ou version ultérieure

  - 64 giga-octets (Go) de mémoire vive (RAM) ECC 

  - Quatre disques SAS de 600 Go (ou supérieur) à 10 000 tr/min, 128 Mo de mémoire cache, 6 Gbits/s, mis en œuvre dans une configuration RAID 5

  - Trois cartes réseau 1 Gbits/s RJ45 haut débit

- Si vous choisissez de déployer la version réduite de l’édition Cloud Connector qui prend en charge jusqu’à 50 appels simultanés, vous aurez besoin des éléments suivants:

  - Intel i7 4790 quad core avec Intel 4600 Graphics (pas besoin de carte graphique haut de gamme)

  - 32 Go DDR3-1600 non ECC

  - 2 : 1 To 7200 RPM Serial Attached SCSI III (6 Go/s), RAID 0

  - 2 : Ethernet 1 Go/s (RJ45)

- Si un serveur proxy est requis sur un ordinateur hôte à des fins de navigation sur Internet, appliquez les modifications de configuration suivantes :

  - Pour ignorer le proxy, spécifiez les paramètres de proxy WinHTTP définis avec votre serveur proxy et une liste de contournement incluant le «192.168.213. \*«réseau utilisé par les services de gestion des connecteurs Cloud et sous-réseau Corpnet Skype entreprise tels qu’ils sont définis dans votre fichier CloudConnector. ini. Sinon, la connectivité de la gestion échouera et empêchera le déploiement et la récupération automatique de Cloud Connector. Voici un exemple de commande de configuration de WinHTTP: netsh WinHTTP Set proxy "10.10.10.175:8080" Bypass-List =\*". local; 1. \*; 172,20. \*; 192.168.218. \*'\<local\>".

  - Spécifiez les paramètres proxy par ordinateur au lieu de les spécifier par utilisateur. Dans le cas contraire, les téléchargements de connecteur Cloud échoueront. Vous pouvez spécifier des paramètres proxy par ordinateur en modifiant le registre ou via le paramètre de stratégie de groupe comme suit :

  - **Registre:** Paramètres HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet] ProxySettingsPerUser DWORD: 00000000

  - **Stratégie de groupe:** Modèles\>\>d’administration ordinateur composants\> Windows Internet Explorer: définir les paramètres de proxy par ordinateur (plutôt que par utilisateur)

- Système PBX/jonction ou SBC/passerelle qualifié (un minimum de deux passerelles est recommandé).

    Cloud Connector prend en charge les mêmes contrôleurs SBC (Session Border Controller) que ceux certifiés pour Skype Entreprise. Pour plus d’informations, reportez-vous à la rubrique [infrastructure de téléphonie pour Skype entreprise](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

- Compte d’administrateur de serveur local qui dispose des autorisations pour installer et configurer Hyper-V sur les serveurs hôtes. Le compte doit disposer des autorisations d'administrateur sur le serveur local sur lequel Hyper V est installé et configuré.

- Lors du déploiement, vous devrez créer un compte d'administrateur de domaine avec les autorisations de création et de publication de la topologie dans le domaine Cloud Connector. 

- Enregistrements DNS externes définis dans le fichier CloudConnector.ini inclus dans le package d'installation :

  - Enregistrement DNS externe pour le service Edge d’accès du composant Edge; par exemple, AP.\<Domain Name\>. Vous aurez besoin d'un enregistrement par site PSTN. Cet enregistrement doit contenir les adresses IP de tous les Edges de ce site.

- Un client Office 365 avec les enregistrements DNS et SRV requis créés.

    > [!IMPORTANT]
    > Lorsque vous intégrez votre client à la version Cloud Connector, l’utilisation du suffixe de domaine par défaut,. onmicrosoft.com, en tant que domaine SIP pour votre organisation n’est pas prise en charge. > vous ne pouvez pas utiliser SIP. \<Nom\> de domaine en tant que nom de votre interface de proxy d’accès Edge du Cloud Connector, car cet enregistrement DNS est utilisé par Office 365.

- Un certificat pour le serveur Edge externe obtenu auprès d'une autorité de certification publique (CA).

- Des règles de pare-feu visant à autoriser le trafic via les ports nécessaires ont été définies.

- Une connexion à Internet pour l'ordinateur hôte et les machines virtuelles. Le Cloud Connector télécharge certains logiciels à partir d’Internet. par conséquent, vous devez fournir des informations de passerelle et de serveur DNS de sorte que l’ordinateur hôte du Cloud Connector et les VM puissent se connecter à Internet et télécharger les logiciels nécessaires.

- Un module PowerShell en client distant installé sur l'ordinateur hôte.

- Les informations d'identification d'administrateur de Skype Entreprise Office 365 pour exécuter PowerShell en client distant.

    > [!IMPORTANT]
    > L'authentification multi-facteur NE DOIT PAS être activée pour le compte administrateur.

> [!NOTE]
> Le déploiement Cloud Connector est uniquement pris en charge sur la plateforme virtualisée Microsoft Hyper-V. Les autres plateformes, comme VMware et Amazon Web Services, ne le prennent pas en charge.

> [!NOTE]
> La configuration minimale requise pour exécuter le Cloud Connector est basée sur la capacité matérielle de base (cœurs, MHz, giga-octets, etc.), avec une mémoire tampon permettant de répondre aux problèmes de performance intangibles dans l’architecture de n’importe quel ordinateur. Microsoft a exécuté une vérification de la pire charge de cas sur du matériel disponible dans le commerce en s'appuyant sur une aide minimum. La qualité multimédia et les performances du système sont vérifiées. Les partenaires de l’application officiels de connecteur Cloud de Microsoft disposent d’implémentations matérielles de connecteur Cloud spécifiques pour lesquelles ils ont un niveau de performance soumis à des tests indépendants.

> [!NOTE]
> Les appareils produits par AudioCodes et Sonus ont modifié le code et fonctionné sur une version de serveurs de Windows Server Standard. Ces appareils sont pris en charge.

## <a name="information-you-need-to-gather-before-deployment"></a>Informations dont vous avez besoin pour rassembler le déploiement
<a name="BKMK_PlanDeployment"> </a>

Avant de commencer votre déploiement, vous devez déterminer sa taille, les domaines SIP pris en charge et les informations de configuration pour chacun des sites PSTN à déployer. Pour commencer, vous devez :

- Identifiez tous les domaines SIP qu’il sera desservi par ce déploiement en fonction des URI SIP utilisés au sein de votre entreprise.

- déterminer le nombre de sites PSTN à déployer ;

- Assurez-vous que le matériel requis pour la prise en charge des quatre VM s’installe pour chaque édition Cloud Connector.

Pour chaque site PSTN que vous envisagez de déployer, vous devez:

- Créer des noms pour tous les composants de chaque matériel de connecteur Cloud (voir [déterminer les paramètres de déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)).

- Définir des plages de ports (reportez-vous à la rubrique [Ports et protocoles](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)) ; 

- créer des enregistrements DNS externes pour le composant Edge (reportez-vous à la rubrique [Requirements for deployment](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)) ;

- déterminer les exigences en matière de certificats pour le composant Edge (reportez-vous à la rubrique [Certificate requirements](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)).

### <a name="ports-and-protocols"></a>Ports et protocoles
<a name="BKMB_Ports"> </a>

Lors de la définition des plages de ports multimédias, gardez les points suivants à l'esprit :

- Les clients utilisent toujours la plage de ports 50000 à 50019 pour le trafic multimédia: cette gamme est prédéfinie dans Skype entreprise Online et ne peut pas être modifiée.

- Le composant de médiation utilise, par défaut, la plage de ports comprise entre 49 152 et 57 500 pour le trafic multimédia. Toutefois, la connexion est établie par le biais d’un pare-feu interne et, pour des raisons de sécurité, vous pouvez limiter cette portée de port dans votre topologie. Vous devrez compter jusqu'à 4 ports par appel. Si vous souhaitez limiter le nombre de ports entre le composant de médiation et la passerelle PSTN, vous devrez également configurer la plage de ports correspondante sur la passerelle.

- Vous devez déployer le connecteur Cloud dans un réseau de périmètre. Cela signifie que vous aurez deux pare-feu :

  - Le premier pare-feu est externe, entre Internet et votre réseau de périmètre.

  - Le deuxième pare-feu est interne entre le réseau de périmètre et votre réseau interne.

    Vos clients peuvent se trouver sur Internet ou sur le réseau interne : 

  - Les clients sur Internet se connectent à votre réseau téléphonique public commuté (RTC) via le pare-feu externe, à travers le composant Edge.

  - Les clients du réseau interne se connectent via le pare-feu interne au composant médiation du réseau de périmètre, qui connecte le trafic à la passerelle SBC ou PSTN.

    Vous devez donc ouvrir des ports dans les deux pare-feu. 

Les tableaux ci-dessous décrivent les ports et les plages de ports pour les pare-feu externe et interne.

Ce tableau indique les ports et les plages de ports permettant la communication entre les clients sur le réseau interne et le composant de médiation :

**Pare-feu interne**



|**Adresse IP source**|**Adresse IP de destination**|**Port source**|**Port de destination**|
|:-----|:-----|:-----|:-----|
|Composant médiation du Cloud Connector  <br/> |Passerelle SBC/PSTN  <br/> |Indifférente  <br/> |TCP 5060\*\*  <br/> |
|Passerelle SBC/PSTN  <br/> |Composant médiation du Cloud Connector  <br/> |Indifférente  <br/> |TCP 5068/TLS 5067  <br/> |
|Composant médiation du Cloud Connector  <br/> |Passerelle SBC/PSTN  <br/> |UDP 49 152-57 500  <br/> |Y\*\*\*  <br/> |
|Passerelle SBC/PSTN  <br/> |Composant médiation du Cloud Connector  <br/> |Y\*\*\*  <br/> |UDP 49 152-57 500  <br/> |
|Composant médiation du Cloud Connector  <br/> |Clients internes  <br/> |TCP 49 152-57 500\*  <br/> |TCP 50 000 à 50 019  <br/> (Facultatif)  <br/> |
|Composant médiation du Cloud Connector  <br/> |Clients internes  <br/> |UDP 49 152-57 500\*  <br/> |UDP 50 000 à 50 019  <br/> |
|Clients internes  <br/> |Composant médiation du Cloud Connector  <br/> |TCP 50 000 à 50 019  <br/> |TCP 49 152-57 500\*  <br/> |
|Clients internes  <br/> |Composant médiation du Cloud Connector  <br/> |UDP 50 000 à 50 019  <br/> |UDP 49 152-57 500\*  <br/> |

\*Il s’agit de la plage de port par défaut sur le composant de médiation. Pour obtenir un flux d'appels optimal, quatre ports par appel sont nécessaires.

\*\*Ce port doit être configuré sur la passerelle SBC/PSTN; par exemple, 5060. Vous pouvez configurer d’autres ports sur votre passerelle SBC/PSTN.

\*\*\*Notez que vous pouvez également limiter la portée de port de votre SBC/passerelle si le fabricant SBC/passerelle l’autorise.

Pour des raisons de sécurité, vous pouvez limiter la plage de ports pour le composant de médiation à l’aide de l’applet de action [Set-CsMediationServer](https://docs.microsoft.com/powershell/module/skype/set-csmediationserver?view=skype-ps) .

Par exemple, la commande suivante permet de limiter le nombre de ports que le composant de médiation utilisera pour le trafic multimédia vers 50 000-51 000 pour le son (en entrée et en sortie). Avec cette configuration, le composant de médiation pourra traiter 250 appels simultanés. Notez que vous souhaiterez peut-être également limiter cette plage sur la passerelle SBC/PSTN :

```
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

Pour récupérer le nom du composant de médiation et voir les ports par défaut, vous pouvez utiliser l’applet de passe [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps) en procédant comme suit:

```
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

Le tableau suivant répertorie les ports et les plages de ports permettant de permettre la communication entre le composant Edge du connecteur Cloud et le pare-feu externe. Ce tableau indique la configuration minimale recommandée.

Dans le cas présent, tout le trafic multimédia vers Internet est acheminé via le bord en ligne comme suit: point de terminaison\>de l’utilisateur:\>connecteur Edge-Cloud en ligne:

**Pare-feu externe - configuration minimale**



|**Adresse IP source**|**Adresse IP de destination**|**Port source**|**Port de destination**|
|:-----|:-----|:-----|:-----|
|Indifférente  <br/> |Interface externe latérale du Cloud Connector  <br/> |Indifférente  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externe latérale du Cloud Connector  <br/> |Indifférente   <br/> |Indifférente  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externe latérale du Cloud Connector  <br/> |Indifférente   <br/> |Indifférente  <br/> |TCP 80  <br/> |
|Interface externe latérale du Cloud Connector  <br/> |Indifférente   <br/> |Indifférente  <br/> |UDP 53  <br/> |
|Interface externe latérale du Cloud Connector  <br/> |Indifférente   <br/> |Indifférente  <br/> |TCP 53  <br/> |
|Interface externe latérale du Cloud Connector  <br/> |Indifférente  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Indifférente  <br/> |Interface externe latérale du Cloud Connector  <br/> |TCP 50 000 à 59 999  <br/> |TCP 443  <br/> |
|Indifférente  <br/> |Interface externe latérale du Cloud Connector  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Interface externe latérale du Cloud Connector  <br/> |Indifférente  <br/> |TCP 50 000 à 59 999  <br/> |TCP 443  <br/> |

Le tableau suivant répertorie les ports et les plages de port pour permettre la communication entre le composant Edge du connecteur Cloud et le pare-feu externe. Le tableau suivant indique la solution recommandée.

Dans ce cas, le trafic multimédia pour le point de terminaison sur Internet peut être acheminé directement vers le composant Edge du Cloud Connector. Le chemin multimédia sera le point de terminaison de\> l’utilisateur.

> [!NOTE]
> Cette solution ne fonctionne pas si le point de terminaison utilisateur est protégé par une fonction de conversion d'adresses réseau (NAT) symétrique.

**Pare-feu externe - configuration recommandée**


|**Adresse IP source**|**Adresse IP de destination**|**Port source**|**Port de destination**|
|:-----|:-----|:-----|:-----|
|Indifférente  <br/> |Interface externe latérale du Cloud Connector  <br/> |Indifférente  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externe latérale du Cloud Connector  <br/> |Indifférente   <br/> |Indifférente  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externe latérale du Cloud Connector  <br/> |Indifférente   <br/> |Indifférente  <br/> |TCP 80  <br/> |
|Interface externe latérale du Cloud Connector  <br/> |Indifférente   <br/> |Indifférente  <br/> |UDP 53  <br/> |
|Interface externe latérale du Cloud Connector  <br/> |Indifférente   <br/> |Indifférente  <br/> |TCP 53  <br/> |
|Interface externe latérale du Cloud Connector  <br/> |Indifférente  <br/> |TCP 50 000 à 59 999  <br/> |Indifférente  <br/> |
|Interface externe latérale du Cloud Connector  <br/> |Indifférente  <br/> |UDP 3 478 ; UDP 50 000 à 59 999  <br/> |Indifférente   <br/> |
|Indifférente  <br/> |Interface externe latérale du Cloud Connector  <br/> |Indifférente  <br/> |TCP 443 ; TCP 50 000 à 59 999  <br/> |
|Indifférente  <br/> |Interface externe latérale du Cloud Connector  <br/> |Indifférente  <br/> |UDP 3478 ; UDP 50 000 à 59 999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>Conditions requises de l'hôte pour la connexion Internet
<a name="BKMB_Ports"> </a>

L’ordinateur hôte doit être en mesure d’accéder aux ressources externes pour pouvoir installer, mettre à jour et gérer le Cloud Connector. Le tableau suivant indique les destinations et ports nécessaires entre l'ordinateur hôte et les ressources externes.

|Direction  <br/> |Adresse IP source  <br/> |Adresse IP de destination  <br/> |Port source  <br/> |Port de destination  <br/> |Protocole  <br/> |Objectif  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sortant  <br/> |IPs du centre de connexion Cloud  <br/> |indifférente  <br/> |indifférente  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|Sortant  <br/> |IPs du centre de connexion Cloud  <br/> |indifférente  <br/> |indifférente  <br/> |80, 443  <br/> |TCP  <br/> |Liste de révocation de certificats (CRL)  <br/> |
|Sortant  <br/> |IPs hôte sur le Cloud Connector  <br/> |indifférente  <br/> |indifférente  <br/> |80, 443  <br/> |TCP  <br/> |Mise à jour du Cloud Connector  <br/> Skype Entreprise Online  <br/> Administrateur PowerShell  <br/> Windows Update  <br/> |

Si des règles plus restrictives sont nécessaires, consultez les URL suivantes sur liste blanche :

- [URL](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) de la liste de révocation de certificats dans [les URL et plages d’adresses IP 365 Office](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)

- Windows Update: [configuration d’un pare-feu pour les mises à jour logicielles](https://technet.microsoft.com/en-us/library/bb693717.aspx)

- PowerShell d’administration de Skype entreprise Online \*:. online.Lync.com

    Si une exclusion de proxy est nécessaire pour cette destination, vous devrez l'ajouter à la liste de contournement WinHTTP.

- Mise à jour du connecteur Cloud: [https://go.microsoft.com](https://go.microsoft.com)Centre de [Téléchargement](https://aka.ms/CloudConnectorInstaller), et[https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>Résolution des noms DNS pour le composant Edge
<a name="BKMB_Ports"> </a>

Le composant Edge doit résoudre les noms externes des services 365 Office et les noms internes des autres composants Cloud Connector.

Chaque composant Edge est un ordinateur à plusieurs connexions avec des interfaces interne et externe. Cloud Connector déploie les serveurs DNS sur le composant contrôleur de domaine au sein du réseau de périmètre. Vous pouvez pointer vers le serveur Edge du serveur DNS au sein du périmètre pour toutes les résolutions de nom, mais vous devez activer le serveur DNS de connexion Cloud pour résoudre les noms externes en définissant une zone DNS contenant un ou plusieurs enregistrements DNS A pour les requêtes externes qui font référence à des noms recherche sur d’autres serveurs DNS publics.

Dans le fichier .ini, si vous définissez comme domaine SIP le nom de domaine complet des passerelles du même domaine, la zone faisant autorité pour ce domaine SIP sera créée dans le serveur DNS au sein du périmètre. Si Edge Server est pointé vers ce serveur DNS pour résoudre les noms, Edge ne résoudra jamais le _sipfederationtls. \<votre_domaine\> DNS record, qui est requis pour le flux d’appels. Dans ce cas, nous vous recommandons de fournir un serveur DNS sur l’interface externe latérale pour résoudre les recherches de noms Internet et chaque composant Edge doit utiliser un fichier hôte pour résoudre d’autres noms de composant Cloud Connector en adresses IP.

> [!NOTE]
> Pour des raisons de sécurité, nous vous conseillons de ne pas faire pointer vers les serveurs internes du domaine de production pour la résolution de nom.

### <a name="determine-deployment-parameters"></a>Définition des paramètres de déploiement
<a name="BKMK_SiteParams"> </a>

Vous devez d'abord définir les paramètres de déploiement communs suivants :


|**Option**|**Description**|**Remarques**|
|:-----|:-----|:-----|
|Domaines SIP  <br/> |URI SIP utilisée par les utilisateurs de l’entreprise. Fournit tous les domaines SIP pris en charge par ce déploiement. Vous pouvez disposer de plusieurs domaines SIP.  <br/> ||
|Nombre de sites PSTN  <br/> |Nombre de sites PSTN que vous allez déployer.  <br/> ||

Pour chaque site PSTN que vous envisagez de déployer, vous devrez rassembler les informations suivantes avant de commencer le déploiement. Vous devrez fournir ces informations lorsque vous mettez à jour le fichier CloudConnector.ini.

Lorsque vous configurez les informations de la passerelle, gardez à l'esprit les points suivants :

- Si vous disposez d'une seule passerelle, supprimez la section « deuxième passerelle » dans le fichier .ini. S'il y a plus de deux passerelles, suivez le format existant pour en ajouter de nouvelles.

- Assurez-vous que l'adresse IP et le port de la(des) passerelle(s) soit correcte.

- Pour permettre une haute disponibilité de la passerelle PSTN, conservez la passerelle secondaire ou ajoutez des passerelles.

(Facultatif) Pour limiter les numéros d'appels sortants, mettez à jour la valeur LocalRoute.



|**Paramètres de site**|**Description**|**Remarques**|
|:-----|:-----|:-----|
|Nom de domaine de la machine virtuelle  <br/> |Nom de domaine pour les composants internes du Cloud Connector. Ce domaine doit être différent du domaine de production. Il peut s'agir du même nom sur toutes les appliances de Cloud Connector.  <br/> Nom dans le fichier. ini: «VirtualMachineDomain»  <br/> |.domaine local recommandé.   <br/> |
|Nom du contrôleur de domaine Cloud Connector  <br/> |Nom du contrôleur de domaine.   <br/> Nom dans le fichier. ini: "NomServeur"  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> |
|Contrôleur de domaine IP/réseau du Cloud Connector  <br/> |Adresse IP du contrôleur de domaine.   <br/> Nom dans le fichier. ini: "IP"  <br/> ||
|Noms de domaine complet des services en ligne O365  <br/> |Doit être la valeur par défaut dans la plupart des cas pour l’instance O365 dans le monde.  <br/> Nom dans le fichier. ini: «OnlineSipFederationFqdn»  <br/> ||
|SiteName  <br/> |Nom du site Skype entreprise; par exemple, Seattle.  <br/> Nom dans le fichier. ini: "SiteName"  <br/> Pour la version 1.4.1 et les suivantes, le nom du site doit être différent pour chaque site, et le nom doit correspondre au site PSTN, s'il existe, défini dans Office 365. Notez que les sites PSTN sont automatiquement créés au moment de l'inscription de la première appliance dans un site.  <br/> ||
|HardwareType  <br/> Version 1.4.1 et suivantes  <br/> |Type de matériel. La valeur par défaut est Normal. Vous pouvez également la définir sur Minimum.  <br/> ||
|Indicatif du pays  <br/> |Indicatif du pays/de la région pour la numérotation.  <br/> Nom dans le fichier. ini: "CountryCode"  <br/> ||
|Ville  <br/> |Ville (facultatif).  <br/> Nom dans le fichier. ini: "City"  <br/> ||
|État  <br/> |État (facultatif).  <br/> Nom dans le fichier. ini: «état»  <br/> ||
|Adresse IP des machines virtuelles de base  <br/> |Adresse IP de l’ordinateur virtuel de base temporaire qui sera utilisée pour créer le VHDX pour toutes les machines virtuelles de connexion Cloud. Cette IP doit se trouver dans le même sous-réseau de réseau de périmètre d'entreprise défini dans l'étape suivante et requiert un accès Internet. Veillez à définir la passerelle par défaut et le DNS d'entreprise routable à Internet.  <br/> Nom dans le fichier. ini: «BaseVMIP»  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> Version 1.4.1 et suivantes  <br/> |L'adresse des services de mises à jour de serveur Windows (WSUS), un serveur intranet qui héberge les mises à jour depuis Microsoft Update.  <br/> Vous pouvez ne rien écrire si vous n'avez pas besoin de WSUS.   <br/> ||
|Masque de sous-réseau pour réseau interne  <br/> |Le connecteur Cloud configure un réseau IP pour les communications internes entre les composants Cloud Connector. Edge doit également être connecté à un autre sous-réseau qui permet la connexion à Internet.  <br/> Nommez le fichier. ini: «CorpnetIPPrefixLength» sous «paramètres pour un pool de réseaux d’ordinateurs virtuels».  <br/> ||
|Masque de sous-réseau pour réseau externe   <br/> |Pour le réseau externe du composant Edge.  <br/> Nommez le fichier. ini: «InternetIPPrefix» sous «paramètres pour un pool de réseaux d’ordinateurs virtuels».  <br/> ||
|Nom du commutateur pour réseau interne  <br/> |Nom du commutateur qui sera utilisé pour le réseau interne du connecteur Cloud.  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nommez le fichier. ini: «CorpnetSwitchName» sous «paramètres pour un pool de réseaux d’ordinateurs virtuels».  <br/> ||
|Nom du commutateur pour réseau externe  <br/> |Nom du commutateur qui sera utilisé pour le réseau de connexion Cloud externe.  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nommez le fichier. ini: «InternetSwitchName» sous «paramètres pour un pool de réseaux d’ordinateurs virtuels».  <br/> ||
|Passerelle par défaut pour le réseau interne  <br/> |Cette passerelle doit permettre l’accès à Internet (Internet requiert également la définition du serveur DNS) et sera configuré sur les interfaces internes des composants Cloud Connector.  <br/> Nommez le fichier. ini: «CorpnetDefaultGateway» sous «paramètres pour un pool de réseaux d’ordinateurs virtuels».  <br/> ||
|Passerelle par défaut pour l'interface externe du composant Edge  <br/> |Sera configurée sur l'interface externe du composant Edge.  <br/> Nommez le fichier. ini: «InternetDefaultGateway» sous «paramètres pour un pool de réseaux d’ordinateurs virtuels».  <br/> ||
|Serveur DNS pour réseau interne  <br/> |Sera configuré sur l'interface interne de la machine virtuelle temporaire. Doit fournir une résolution de noms pour les noms Internet. Si aucun serveur DNS n'est fourni, la connexion à Internet sera impossible et le déploiement ne s'achèvera pas.  <br/> Nommez le fichier. ini: «CorpnetDNSIPAddress» sous «paramètres pour un pool de réseaux d’ordinateurs virtuels».  <br/> ||
|Serveur DNS pour interface externe du composant Edge  <br/> |Sera configuré sur l'interface externe du serveur Edge.  <br/> Nommez le fichier. ini: «InternetDNSIPAddress» sous «paramètres pour un pool de réseaux d’ordinateurs virtuels».  <br/> ||
|Nom du commutateur de gestion  <br/> |Le commutateur de gestion est un commutateur temporaire qui sera créé automatiquement et utilisé pour la configuration de Cloud Connector lors du déploiement. Il sera également déconnecté automatiquement après le déploiement. Il doit s’agir d’un sous-réseau différent de tout autre réseau utilisé dans Cloud Connector.  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nommez le fichier. ini: «ManagementSwitchName» sous «paramètres pour un pool de réseaux d’ordinateurs virtuels».  <br/> ||
|Masque de sous-réseau/adresse du sous-réseau de gestion  <br/> |Le sous-réseau de gestion est un sous-réseau temporaire qui sera créé automatiquement et utilisé pour la configuration de Cloud Connector pendant le déploiement. Il sera également déconnecté automatiquement après le déploiement. Il doit s’agir d’un sous-réseau différent de tout autre réseau utilisé dans Cloud Connector.  <br/> Les noms figurant dans le fichier. ini: «ManagementIPPrefix» et «ManagementIPPrefixLength» sous «paramètres d’un pool de réseaux d’ordinateurs virtuels».  <br/> ||
|Ordinateur de magasin de gestion central (CMS)  <br/> |Nom de domaine complet unique utilisé pour le magasin central de gestion (CMS). Le nom du domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nom dans le fichier. ini: «ServerName» sous «paramètres pour le service de gestion central principal  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> (Nom du pool CMS = Nom du serveur)  <br/> |
|Adresse IP de la machine du magasin central de gestion  <br/> |Adresse IP du serveur CMS (interne dans le réseau de périmètre).  <br/> Nom dans le fichier INI: «IP» sous paramètres pour le service de gestion central principal  <br/> ||
|Nom du partage de fichiers   <br/> |Nom de partage de fichiers à créer sur le serveur CMS pour les données de réplication Skype entreprise (par exemple, CmsFileStore).  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nommez le fichier. ini: «CmsFileStore» sous «paramètres pour le service de gestion central principal».  <br/> ||
|Nom du pool de composants de médiation  <br/> |Nom du pool du composant de médiation. Entrez le nom NETBIOS uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nommez le fichier. ini: «PoolName» sous «paramètres pour un pool de serveurs de médiation».  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> |
|Nom du composant de médiation  <br/> |Nom du composant de médiation 1. Entrez le nom NETBIOS uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nom dans le fichier. ini: "ServerName" sous "paramètres pour un pool de serveurs de médiation"  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> |
|Adresse IP de l’ordinateur du composant de médiation  <br/> |Protocole corpnet IP interne pour le composant de médiation (interne dans le réseau de périmètre).  <br/> Nom dans le fichier. ini: «IP» sous les paramètres d’un pool de serveurs de médiation  <br/> ||
|Nom interne du pool du serveur Edge  <br/> |Nom du pool du composant Edge. Entrez le nom NETBIOS uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nommez le fichier. ini: «InternalPoolName» sous «paramètres pour un pool de serveurs Edge».  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> |
|Nom interne du serveur Edge  <br/> |Nom du composant Edge. Entrez un nom Netbios uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.   <br/> Nommez le fichier. ini: «InternalServerName» sous «paramètres pour un pool de serveurs Edge».  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> |
|Adresse IP interne du serveur Edge   <br/> |Adresse IP du réseau de périmètre interne du composant Edge pour communiquer avec d’autres composants du Cloud Connector.  <br/> Nommez le fichier. ini: «InternalServerIPs» sous «paramètres pour un pool de serveurs Edge».  <br/> ||
|Nom externe du pool d'accès  <br/> |Nom du serveur Edge d'accès, par exemple, AP. Ce nom doit correspondre au nom indiqué pour le certificat SSL. Entrez un nom Netbios uniquement. Le nom de domaine SIP sera utilisé pour générer le nom de domaine complet. Un nom de pool externe est utilisé pour tous les composants Edge du pool. Un pool d’accès Edge est requis par site PSTN.  <br/> Nommez le fichier. ini: «ExternalSIPPoolName» sous «paramètres pour un pool de serveurs Edge».  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> le "SIP" est réservé et ne peut donc pas être utilisé comme nom.  <br/> Le nom de domaine complet généré doit correspondre au nom fourni pour le certificat SSL.   <br/> |
|Adresse IP externe de Edge d’accès  <br/> |Adresse IP externe du composant Edge: adresse IP publique si aucune traduction d’adresses réseau n’est disponible, ou adresse IP traduite (spécifiez les deux adresses si mapped).  <br/> Nommez le fichier. ini: «ExternalSIPIPs» sous «paramètres pour un pool de serveurs Edge».  <br/> ||
|Nom du serveur relais multimédia  <br/> |Nom du serveur Edge du serveur relais multimédia audio/vidéo, par exemple, MR. Un seul nom de pool externe sera utilisé pour tous les composants Edge d'un pool. Un pool de relais de média Edge est requis par site PSTN.  <br/> Nommez le fichier. ini: «ExternalMRFQDNPoolName» sous «paramètres pour un pool de serveurs Edge».  <br/> |Doit faire 15 caractères ou moins. Entrez le nom NETBIOS uniquement.  <br/> |
|Adresse IP externe du Edge du relais multimédia  <br/> |Pour le moment, une seule adresse IP est prise en charge, de sorte qu’il s’agisse d’une adresse IP d’accès public ou d’une adresse IP mappée (spécifiez les deux adresses si mappée). Il peut s’agir d’une adresse identique à l’adresse IP externe du composant Edge. Remarque Si Edge se trouve derrière la traduction d’adresses réseau, vous devez également spécifier la valeur du paramètre Next.  <br/> Nommez le fichier. ini: «ExternalMRIPs» sous «paramètres pour un pool de serveurs Edge».  <br/> ||
|Adresse IP externe du Edge du relais multimédia (si le bord se trouve derrière la NAT)  <br/> |Si votre Edge est protégé par une traduction d'adresse réseau, vous devez également spécifier l'adresse publique du périphérique NAT.  <br/> Nommez le fichier. ini: «ExternalMRPublicIPs» sous «paramètres pour un pool de serveurs Edge».  <br/> ||
|La marque et le modèle de la passerelle vocale 1  <br/> |Indiquez la marque et le modèle de la passerelle SBC/vocale. Notez que vous pouvez connecter un appareil ou un Trunk SIP à partir de la liste des [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP)appareils testés à l’adresse.  <br/> ||
|La marque et le modèle de la passerelle vocale 2 (copier cette ligne si vous avez plus de 2 passerelles)  <br/> |Indiquez la marque et le modèle de la passerelle vocale. Notez que vous pouvez connecter un appareil à partir de la liste des appareils [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP)testés à l’adresse.  <br/> ||
|Nom de la passerelle vocale 1  <br/> |Utilisé pour générer le nom de domaine complet de la machine avec le domaine AD. Nécessaire si TLS est utilisé entre le composant de médiation et la passerelle vocale. Si vous n’avez pas l’intention d’utiliser le nom de domaine complet (par exemple, le protocole TLS n’est pas obligatoire ou si la passerelle vocale ne prend pas en charge la connexion à l’aide du nom de domaine complet)  <br/> ||
|Nom de la passerelle vocale 2 (copier cette ligne si vous avez plus de 2 passerelles)  <br/> |Utilisé pour générer le nom de domaine complet de la machine avec le domaine AD. Nécessaire si TLS est utilisé entre le composant de médiation et la passerelle vocale. Si vous n’avez pas l’intention d’utiliser le nom de domaine complet (par exemple, le protocole TLS n’est pas obligatoire ou si la passerelle vocale ne prend pas en charge la connexion à l’aide du nom de domaine complet)  <br/> ||
|Adresse IP de la passerelle vocale 1  <br/> |Adresse IP de la passerelle vocale.  <br/> ||
|Adresse IP de la passerelle vocale 2 (copier cette ligne si vous avez plus de 2 passerelles)  <br/> |Adresse IP de la passerelle vocale.  <br/> ||
|Passerelle vocale 1 port # (copier cette ligne si vous avez plus de 2 passerelles)  <br/> |Port écouté par la jonction SIP de la passerelle vocale, par exemple, 5 060.  <br/> ||
|Numéro de port de la passerelle vocale 2  <br/> |Port écouté par la jonction SIP de la passerelle vocale, par exemple, 5 060.  <br/> ||
|Protocole SIP passerelle 1 pour le trafic SIP  <br/> |TCP ou TLS.  <br/> ||
|Protocole protocole 2 de passerelle vocale pour le trafic SIP (copier cette ligne si vous avez plus de 2 passerelles)  <br/> |TCP ou TLS.  <br/> ||
|Plage de ports multimédias externes pour le trafic à destination et en provenance du composant Edge  <br/> |Plage de ports TCP/UDP pour le trafic multimédia à destination et en provenance de l'interface externe du composant Edge. Doit toujours commencer à 50 000. Pour plus d’informations, reportez-vous à la section «ports et protocoles».  <br/> |50000 - 59 999  <br/> |
|Plage de port multimédia permettant de communiquer avec le composant de médiation via le pare-feu interne  <br/> |Plage de ports UDP que le composant de médiation utilisera pour communiquer avec les clients et les passerelles (Recommendation 4 ports par appel).  <br/> ||
|Plage de port multimédia pour communiquer avec le client Skype entreprise via un pare-feu interne  <br/> |Ne peut pas être modifiée en raison de la planification. Les ports doivent être ouverts dans le pare-feu interne pour pouvoir communiquer entre les clients Skype entreprise à l’intérieur du réseau interne et le composant de médiation.  <br/> |50 000 à 50 019  <br/> |
|Mot de passe du certificat public  <br/> |Doit être indiqué dans le script.  <br/> ||
|Mot de passe administrateur en mode sans échec  <br/> Version 1.4.2 uniquement  <br/> |Mot de passe administrateur en mode sans échec pour le domaine Cloud Connector interne  <br/> ||
|Mot de passe d’administrateur de domaine Cloud Connector  <br/> Version 1.4.2 uniquement  <br/> |Mot de passe de l’administrateur de domaine Cloud Connector (différent de votre domaine de production). Le nom d'utilisateur est Administrator. Vous ne pouvez pas le modifier.  <br/> ||
|Mot de passe administrateur des machines virtuelles  <br/> Version 1.4.2 uniquement  <br/> |Utilisé pour configurer le réseau de gestion lors du déploiement.  <br/> Le nom d'utilisateur est Administrator. Vous ne pouvez pas le modifier.   <br/> ||
|CABackupFile  <br/> Version 2.0 et ultérieures  <br/> |Utilisé pour l’enregistrement du service d’autorité de certification du serveur Active Directory dans un fichier lors du déploiement de plusieurs appareils dans un site Cloud Connector. Assurez-vous d'utiliser le même mot de passe pour toutes les appliances sur un même site Cloud Connector afin d'importer correctement le fichier de sauvegarde AC vers une nouvelle appliance.  <br/> ||
|CCEService  <br/> Version 2.0 et ultérieures  <br/> |Utilisé pour le service de gestion Cloud Connector ; nécessite l'accès à l'annuaire de site Cloud Connector. Assurez-vous d'utiliser le même mot de passe pour toutes les appliances sur un même site Cloud Connector.   <br/> ||
|Administrateur client Office 365  <br/> | Le compte est utilisé par Cloud Connector pour mettre à jour et gérer les paramètres du client pour Cloud Connector : <br/>  Version 2,0 et versions ultérieures: informations d’identification pour un compte Office 365 dédié avec des droits d’administrateur Skype entreprise. <br/>  Version antérieure à 2.0 : informations d'identification d'un compte Office 365 dédié disposant des droits d'administrateur client global. <br/> ||
|Activer la prise en charge de REFER.  <br/> |Cela déterminera si la prise en charge de SIP REFER est activée ou désactivée sur la configuration de la jonction de votre IP/système PBX. La valeur par défaut est True. Si votre passerelle IP/PBX prend en charge la prise en charge de REFER, veuillez laisser la valeur True. Dans le cas contraire, cette valeur doit être redéfinie sur False. Si vous n’êtes pas sûr que votre passerelle prenne en charge le renvoi de votre adresse, veuillez consulter les [PBX et passerelles IP qualifiés](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).   <br/> ||
|EnableFastFailoverTimer  <br/> Version 2.0 et ultérieures  <br/> |Avec la valeur par défaut «true», si la passerelle ne répond pas aux appels sortants, elle sera routée vers la passerelle disponible suivante; s’il n’y a pas de lignes supplémentaires, l’appel est automatiquement interrompu.  <br/> Cependant, dans une organisation dont les réseaux et les réponses de la passerelle sont lents, ou lorsque la procédure d'établissement d'appel dépasse les 10 secondes, cela peut entraîner l'abandon inutile des appels.  <br/> Lorsque des appels sont passés vers certains pays, par exemple les Émirats arabes unis ou l'Afghanistan, la procédure d'établissement d'appel peut prendre plus de 10 secondes. Si vous rencontrez ces problèmes, vous devrez modifier la valeur en « False ». N'oubliez pas de modifier le paramètre correspondant sur le SBC ou la passerelle connecté(e).  <br/> Les valeurs peuvent être « True » ou « False ». La valeur par défaut est « True ».  <br/> ||
|ForwardCallHistory  <br/> Version 2.0 et ultérieures  <br/> | Ce paramètre est utilisé pour les en-têtes SIP utilisés pour signaler l'appelant initial dans des scénarios de sonnerie simultanée et de transfert d'appel. Définir le paramètre sur « True » entraîne l'activation de deux en-têtes SIP :<br/>  History-Info <br/>  Referred-By <br/>  L’en-tête History-Info est utilisé pour redéfinir le ciblage des demandes SIP et «proposer (s) un mécanisme standard pour capturer les informations de l’historique des demandes afin d’offrir une large gamme de services pour les réseaux et les utilisateurs finaux» ([RFC 4244-Section 1,1](http://www.ietf.org/rfc/rfc4244.txt)). En ce qui concerne les interfaces de jonction de Cloud Connector, elles sont utilisées dans des scénarios de sonnerie simultanée et de transfert d'appel.  <br/>  Les valeurs peuvent être « True » ou « False ». La valeur par défaut est « False ».<br/> ||
|Transfert PAI  <br/> Version 2.0 et ultérieures  <br/> |PAI est une extension privée de SIP qui permet aux serveurs SIP de déclarer l'identité des utilisateurs authentifiés. Pour le fournisseur de jonction SIP, PAI peut être utilisé à des fins de facturation, dans les cas où les en-têtes History-Info et Referred-By sont absents. Lorsque l’option Forward-assertion-Identity est activée dans la configuration, le serveur de médiation transfère les en-têtes &amp; PAI à partir du Cloud Connector sur le Trunk SIP sur le réseau SIP. Le serveur de médiation va transférer les en-têtes PAI avec &amp; les numéros E. 164 de l’URI a uniquement reçus sur le Trunk SIP du Cloud Connector. Le serveur de médiation transférera également tout en-tête Privacy reçu dans l'une des directions. Si la requête SIP envoyée par le serveur de médiation inclut un en-tête de confidentialité de la forme «confidentialité: ID» conjointement avec l’en-tête PAI, l’identité affirmée doit rester privée en dehors du domaine d’approbation du réseau.  <br/> Les valeurs peuvent être « True » ou « False ». La valeur par défaut est « False ».  <br/> ||

### <a name="certificate-requirements"></a>Exigences en matière de certificats
<a name="BKMK_Certs"> </a>

Chaque composant Edge nécessite un certificat délivré par une autorité de certification publique. Les certificats doivent disposer d'une clé privée exportable pour pouvoir être copiés d'un composant Edge à l'autre. Pour respecter ces exigences, vous devrez choisir entre les options ci-après et indiquer le nom de sujet (SN) et un autre nom de sujet (SAN) pour le certificat :

 **Si vous disposez d'un domaine SIP unique :**

- **Option 1.** Le nom de sujet doit contenir le nom du pool affecté aux composants Edge. Notez que le nom de l’objet ne peut pas être sip.sipdomain.com car ce nom est réservé pour le composant Microsoft Edge de Skype entreprise online. L'autre nom de sujet doit contenir sip.sipdomain.com et le nom du pool Edge d'accès :

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **Option 2.** Si vous souhaitez utiliser un certificat générique unique sur tous les serveurs de pools Edge que vous déployez, vous pouvez utiliser une entrée SAN \*de. sipdomain.com au lieu du nom du pool de bords dans le certificat. Le nom de sujet peut être le nom d'un des pools Edge d'accès que vous avez déployés :

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> Vous ne devez pas créer d’entrée DNS externe pour SIP. \<sipdomain\>. com, car ce nom appartient au déploiement d’Office 365.

> [!NOTE]
> Si vous souhaitez utiliser un certificat unique pour tous les pools Edge déployés dans votre organisation et ne pouvez pas utiliser un certificat générique comme défini dans l'option 2, vous devrez alors inclure le nom de domaine complet pour tous les pools Edge déployés dans le nom SAN dans le certificat. 

 **Si vous disposez de plusieurs domaines SIP :**

Vous devez ajouter sip.sipdomain.com pour chaque domaine SIP, ainsi que le nom des pools Edge d'accès par domaine (il peut s'agir d'un pool physique avec des noms différents). Vous trouverez ci-dessous un exemple d'entrées SN et SAN dans un scénario comportant plusieurs domaines SIP :

- **Option 1.** Le nom du sujet doit contenir le nom du pool que vous avez attribué aux composants du bord. Notez que le nom de l’objet ne peut pas être sip.sipdomain.com car ce nom est réservé pour le composant Microsoft Edge de Skype entreprise online. L'autre nom de sujet doit contenir sip.sipdomain.com et le nom du pool Edge d'accès :

  ```
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>Option 2.</strong> Si vous souhaitez utiliser un certificat générique unique sur tous les serveurs de pools Edge que vous déployez, vous pouvez utiliser une entrée SAN \*de. sipdomain.com au lieu du nom du pool de bords dans le certificat. Le nom de sujet peut être le nom d'un des pools Edge d'accès que vous avez déployés :

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> Vous ne devez pas créer d’entrée DNS externe pour SIP. \<sipdomain\>. com, car ce nom appartient au déploiement d’Office 365.

Dans le cadre d'un déploiement, vous pouvez utiliser le tableau suivant :

|**Option**|**Description**|**Remarques**|
|:-----|:-----|:-----|
|Quelle option allez-vous utiliser pour votre déploiement ?  <br/> |Option 1 ou 2  <br/> ||
|SN  <br/> |Indique le nom de sujet du certificat  <br/> ||
|SAN  <br/> |Indique l'autre nom de sujet du certificat  <br/> ||

Si vous utilisez TLS entre la passerelle et le serveur de médiation, vous devrez obtenir le certificat racine ou la chaîne de certificats complète pour le certificat assigné à la passerelle.

## <a name="dial-plan-considerations"></a>Aspects relatifs au plan de numérotation
<a name="BKMK_DailPlan"> </a>

Le Cloud Connector nécessite l’utilisation d’un plan de numérotation en ligne. Pour plus d’informations sur la configuration d’un plan de numérotation en ligne, reportez-vous à la rubrique [qu’est-ce que les plans](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>Considérations relatives à la haute disponibilité
<a name="BKMK_HA"> </a>

Lorsque vous déployez l’édition Cloud Connector pour une disponibilité élevée, vous déployez au moins deux applications qui servent de sauvegarde. Chaque application se compose de quatre composants: Edge, Mediation, Central Management Store (CMS) et Domain Controller.

En règle générale, si un composant au sein d’une appliance est en panne, l’édition Cloud Connector peut continuer à gérer les appels, mais vous devez prendre en compte les éléments suivants:

- **Mediation, CMS et les considérations relatives au composant du contrôleur de domaine**

    Supposons que le composant du contrôleur de domaine ou du magasin central de gestion d'une appliance ne fonctionne pas. L'appliance peut toujours traiter les appels entrants et sortants, mais si vous relancez un composant de médiation lorsque le composant du contrôleur de domaine ou du magasin central de gestion est inaccessible, la médiation ne fonctionnera pas. Vous ferez face à la même situation si vous relancez le composant du magasin central de gestion lorsque le contrôleur de domaine est en panne.

    **Recommandation:** Avant de redémarrer les composants, vérifiez la disponibilité des autres composants de l’application.

- **Considérations relatives au composant Edge**

    Si le composant Edge d'une appliance n'est pas disponible, le comportement des appels entrants et sortants changera, de la façon suivante :

  - **Appel sortant**: appel d’un utilisateur Internet vers un réseau PSTN.

    Le mécanisme de distribution d'appels dans le cloud identifiera le fait que l'un des composants Edge est hors service et acheminera tous les appels vers une autre appliance, afin que l'appel sortant aboutisse.

  - **Appel entrant**(appel entrant du réseau PSTN) à un utilisateur qui se trouve dans un réseau local ou sur Internet.

     Si le composant Edge de l'appliance qui a reçu l'appel ne fonctionne pas, les appels entrants dans cette appliance ne fonctionneront pas, car le composant de médiation ne peut pas rediriger l'appel vers le composant Edge dans l'autre appliance.

    **Recommandation:** Mettre en place un système de contrôle. Une fois que vous avez identifié un dysfonctionnement du composant Edge, fermez tous les composants de l’application où le composant Edge n’est pas disponible.

## <a name="cloud-connector-media-flow"></a>Trafic multimédia de Cloud Connector
<a name="BKMK_MediaFlow"> </a>

Les schémas suivants décrivent le flux d’un appel entrant et sortant via la version Cloud Connector. Ces informations sont utiles pour comprendre comment la connexion est établie.

Sur la première illustration, un utilisateur interne passe un appel sortant, comme suit :

1. Dave, un utilisateur hébergé en ligne, mais qui se trouve actuellement sur le réseau interne, appelle un utilisateur RTC externe.

2. Le trafic SIP est acheminé vers Skype entreprise online.

3. Skype entreprise Online effectue une recherche de numéro inverse du numéro. La recherche du numéro inverse échoue, car ce numéro n’appartient à aucun utilisateur de l’organisation Skype entreprise.

4. L'appel est acheminé vers le composant Edge (trafic SIP et multimédia par le biais du composant Online Edge dans un premier temps, puis le trafic multimédia vers le composant de médiation par le biais du pare-feu interne).

5. Si l'itinéraire existe, le composant Edge relaie le trafic vers le composant de médiation dans le réseau de périmètre.

6. Le composant de médiation envoie le trafic vers la passerelle PSTN.

![Flux de média sortant pour Cloud Connector](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

Sur l'illustration ci-dessous, un utilisateur interne reçoit un appel entrant comme suit :

1. La passerelle PSTN reçoit un appel pour l'utilisateur Dave, qui est hébergé en ligne, mais se trouve actuellement sur le réseau interne.

2. Le trafic SIP est acheminé vers le composant de médiation.

3. Le composant de médiation envoie le trafic SIP au composant Edge, puis il passe dans Skype entreprise online.

4. Skype entreprise Online effectue une recherche de numéro inverse du numéro et constate qu’il s’agit de Dave de l’utilisateur.

5. La signalisation SIP est envoyée vers tous les points de présence de Dave.

6. Le trafic multimédia est établi entre la passerelle et le composant de médiation et entre le composant de médiation et le point de terminaison.

![Flux de média entrant pour Cloud Connector](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>Analyse et résolution des problèmes
<a name="BKMK_Monitor"> </a>

Le mécanisme d'analyse et de résolution des problèmes est installé automatiquement avec chaque appliance Cloud Connector. Le mécanisme détecte les événements suivants :

- Un ou plusieurs ordinateurs d'une appliance Cloud Connector ne sont pas connectés à un commutateur virtuel interne ou internet.

- Un ou plusieurs ordinateurs d'une appliance Cloud Connector sont en état Enregistré ou Arrêté.

- Les services ne sont pas exécutés.

  Si l’un des événements suivants est détecté, l’ensemble de l’application Cloud Connector est vidé et marqué comme étant hors ligne pour empêcher toute tentative d’établissement d’appels vers une appliance qui ne fonctionne pas correctement. Les fonctionnalités de récupération automatique de Cloud Connector restaureront ensuite les services et marqueront l'appliance comme étant en ligne. Si la récupération automatique échoue pour une raison quelconque, reportez-vous à [Troubleshoot your Cloud Connector deployment](troubleshoot-your-cloud-connector-deployment.md).

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

Pour plus d'informations, voir les articles suivants :

- [Détails sur les solutions téléphoniques Microsoft Telephony](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)

- [Configuration et gestion de Skype Entreprise, version Cloud Connector](configure-skype-for-business-cloud-connector-edition.md)

- [Planifier le contournement de média dans Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

- [Contournement du déploiement multimédia dans la version Cloud Connector](deploy-media-bypass-in-cloud-connector.md)


