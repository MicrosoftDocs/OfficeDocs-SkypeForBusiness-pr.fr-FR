---
title: Planifier les Skype Entreprise Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6ce0e580-8c4a-45de-a54f-e39e438335d6
description: Recherchez des informations sur Skype Entreprise Cloud Connector Edition, un ensemble de machines virtuelles (VM) qui implémentent la connectivité PSTN sur site avec Système téléphonique (PBX cloud).
ms.openlocfilehash: f27fdd41978cd686a7019876dedbfe63a29af9e9
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014148"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Planifier les Skype Entreprise Cloud Connector Edition

> [!Important]
> Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online. Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)

Recherchez des informations sur Skype Entreprise Cloud Connector Edition, un ensemble de machines virtuelles (VM) qui implémentent la connectivité PSTN sur site avec Système téléphonique (PBX cloud).

Cloud Connector Edition peut être la solution appropriée pour votre organisation si vous n’avez pas encore de déploiement Lync Server ou Skype Entreprise Server existant. Si vous étudiez toujours quelle solution Système téléphonique est adaptée à votre entreprise, consultez [solutions de téléphonie Microsoft.](/microsoftteams/cloud-voice-landing-page)

Ce document décrit les conditions requises de l’édition Cloud Connector et les topologies pris en charge, et vous aide à planifier votre déploiement de la version Cloud Connector. Veillez à lire cet article avant de configurer votre environnement Cloud Connector. Lorsque vous êtes prêt à déployer et configurer l’édition Cloud Connector, voir Configurer et [gérer Skype Entreprise Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md).

Cloud Connector Edition 2.1 est désormais disponible. Si vous n’avez pas encore mis à niveau vers la version 2.1, voir Mise à niveau vers [une nouvelle version de Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md). Vous trouverez le fichier d’installation sur [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .

> [!NOTE]
> Microsoft prend en charge la version précédente de Cloud Connector pendant 60 jours après la publication d’une nouvelle version. Microsoft prendra en charge la version 2.0.1 pendant 60 jours après la publication de la version 2.1 pour vous laisser le temps de mettre à niveau. Toutes les versions antérieures à la version 2.0.1 ne sont plus pris en charge.

Cloud Connector Edition est une offre hybride qui se compose d’un ensemble de machines virtuelles (VM) qui implémentent la connectivité PSTN sur site avec Système téléphonique. En déployant une topologie Skype Entreprise Server minimale dans un environnement virtualisé, les utilisateurs de votre organisation qui sont dans le cloud peuvent recevoir des services PBX à partir du cloud Microsoft, mais la connectivité PSTN est fournie par le biais de l’infrastructure vocale locale existante.

![Diagramme de topologie montrant cloud PBX Gateway connectant CLOUD PBX à un déploiement local de Skype Entreprise.](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

Étant donné que Cloud Connector vous permet d’intégrer des services Système téléphonique à votre environnement de téléphonie existant(par exemple, PBX, périphériques analogiques et centres d’appels), vous pouvez implémenter une migration progressive de votre solution de téléphonie existante vers Système téléphonique.

Par exemple, supposons que votre société possède un centre d’appels sophistiqué avec des fonctionnalités spécifiques Système téléphonique ne fournit pas. Vous pouvez choisir de laisser les utilisateurs du centre d’appels avec la solution existante, mais déplacer d’autres utilisateurs vers Système téléphonique.

Cloud Connector assure le routage entre les utilisateurs sur site et en ligne, et vous pouvez choisir d’utiliser votre propre fournisseur PSTN avec Système téléphonique.

Prenons les considérations suivantes lors de la planification de votre déploiement de la version Cloud Connector :

- Pour utiliser Cloud Connector afin de tirer parti des solutions vocales cloud, vous devez vous inscrire à une organisation Microsoft 365 ou Office 365 qui inclut Système téléphonique. Si vous n’avez pas encore Microsoft 365 ou Office 365 organisation, vous pouvez apprendre à vous inscrire ici : [Microsoft 365 entreprise](https://products.office.com/business/office). Notez que vous devez vous inscrire à un plan qui inclut Skype Entreprise Online.

- Pour inscrire des appliances Cloud Connector avec le service Skype Entreprise Online et exécuter différentes cmdlets, Cloud Connector 2.0 et les ultérieures nécessitent un compte Microsoft 365 ou Office 365 dédié avec les droits d’administrateur client Skype Entreprise. Les versions de Cloud Connector antérieures à la version 2.0 nécessitent un compte Microsoft 365 ou un compte Office 365 avec des droits d’administrateur général client.

- Cloud Connector ne nécessite pas un déploiement complet sur site Skype Entreprise Server déploiement.

    Actuellement, Cloud Connector ne peut pas coexister avec Lync Skype Entreprise serveurs locaux. Si vous souhaitez déplacer des utilisateurs Lync ou Skype Entreprise existants vers Microsoft 365 et continuer à fournir des services téléphoniques locaux à vos utilisateurs, envisagez d’utiliser un déploiement Système téléphonique avec connectivité sur site à l’aide d’un déploiement Skype Entreprise Server existant. Pour plus d’informations, voir [Plan your Système téléphonique (Cloud PBX) solution](/microsoftteams/cloud-voice-landing-page) and Plan Système téléphonique with [on-premises PSTN connectivity in Skype Entreprise Server](plan-phone-system-with-on-premises-pstn-connectivity.md).

- Si vous avez déjà déployé Skype Entreprise ou Lync Server et étendu le schéma, vous n’avez pas besoin de nettoyer le schéma pour le déploiement Cloud Connector, tant que vous avez supprimé tous les composants Skype Entreprise ou Lync Server de votre environnement.

- Vos utilisateurs sont en ligne.

- Si votre organisation a configuré la synchronisation d’annuaires (DirSync), tous les comptes d’utilisateurs planifiés pour la voix hybride doivent d’abord être créés dans votre déploiement local, puis synchronisés avec le cloud.

- Vous pouvez conserver votre opérateur PSTN actuel si nécessaire.

- Si vous souhaitez fournir des conférences à des utilisateurs hébergés sur Cloud Connector, vous pouvez acheter une licence de conférence PSTN ou payer à mesure que vous proposez une offre d’audioconférence de Microsoft.

- La licence d’audioconférence (ou le paiement à mesure que vous proposez) est également requise pour les escalades d’appels. Si un utilisateur Skype Entreprise reçoit un appel d’un utilisateur PSTN externe et souhaite ajouter un participant à cet appel (faire resserre l’appel vers une conférence), l’escalade est effectuée via le service d’audioconférence Microsoft.

- Cloud Connector 2.0 et les ultérieures prend désormais en charge le contournement de média. La déviation du trafic multimédia permet à un client d’envoyer du trafic multimédia directement au saut suivant du réseau téléphonique commuté (PSTN) (passerelle ou contrôleur SBC) et d’éliminer le composant Cloud Connector Edition du chemin d’accès du média. Pour plus d’informations, voir [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).

- Cloud Connector 2.1 et ultérieur prend en charge la surveillance de Cloud Connector à l’aide d’Operations Management Suite (OMS). Pour plus d’informations, voir [Surveiller Cloud Connector à l’aide d’Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

- Cloud Connector est disponible dans tous les pays où Office 365 Entreprise E5 est disponible.

Cet article contient les sections principales suivantes :

- [Composants cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [Topologies Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [Conditions requises pour le déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [Informations à collecter avant le déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [Considérations sur le plan de numérotation](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [Considérations sur la haute disponibilité](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [Flux multimédia Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [Analyse et dépannage](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [Pour plus d'informations](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>Composants cloud Connector Edition
<a name="BKMK_Components"> </a>

Avec Cloud Connector Edition, vous déployez un ensemble de VM empaquetées qui contiennent une topologie Skype Entreprise Server minimale composée d’un composant Edge, d’un composant de médiation et d’un rôle cmS (Central Management Store). Vous installerez également un contrôleur de domaine, qui est requis pour le fonctionnement interne de Cloud Connector. Ces services sont configurés pour être hybrides avec votre organisation Microsoft 365 ou Office 365 qui inclut les services Skype Entreprise Online.

![Composants de la version Cloud Connector.](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

Les composants Cloud Connector fournissent les fonctionnalités suivantes :

- **Composant Edge** : la communication entre la topologie sur site et les services en ligne passe par le composant Edge, qui inclut les composants suivants :

  - **Edge d’accès** : fournit un routage SIP entre le déploiement local et Skype Entreprise Online.

  - **Relais multimédia** : fournit le routage des médias entre le composant de médiation et d’autres points de terminaison multimédias.

  - **Authentification du relais** multimédia / MRAS : génère des jetons pour l’accès au relais multimédia.

- **Routage sortant : assure** l’équilibrage de charge du trafic vocal entre les passerelles ou les contrôleurs SCS connectés à une appliance Cloud Connector. Les appels seront répartis de manière également répartie entre toutes les passerelles ou SCS connectées à l’appliance Cloud Connector.

    Fournit un routage vers les passerelles en fonction des stratégies. Seules les stratégies globales basées sur des numéros PSTN de destination (sortants) sont pris en charge.

- Rôle du magasin central de gestion **(CMS)** : inclut le magasin de configuration pour les composants de topologie, y compris le transfert de fichiers CMS.

- Réplica du magasin central de gestion **(CMS)** : synchronise les informations de configuration de la base de données CMS globale sur le serveur de rôles CMS.

- **Contrôleur de** domaine - Services de domaine Active Directory Cloud Connector pour stocker tous les paramètres et groupes globaux nécessaires au déploiement des composants Cloud Connector. Une forêt sera créée pour chaque appliance Cloud Connector. Le contrôleur de domaine ne doit pas avoir de connexions avec active Directory de production. Les services Active Directory sont les suivants :

  - Services de domaine Active Directory

  - Services de certificats Active Directory pour émettre des certificats internes

- **Composant de médiation** : implémente le protocole de mappage de passerelle SIP et multimédia entre les Skype Entreprise et les passerelles PSTN. Inclut un réplica CMS qui synchronise la configuration à partir de la base de données CMS globale.

## <a name="cloud-connector-edition-topologies"></a>Topologies Cloud Connector Edition
<a name="BKMK_Topologies"> </a>

Dans le cadre de cette discussion, nous allons faire référence aux sites PSTN. Un site PSTN est une combinaison d’appliances Cloud Connector, déployées au même emplacement et avec des passerelles PSTN communes qui leur sont connectées. Les sites PSTN vous permettent de :

- Fournir une connectivité aux passerelles les plus proches de vos utilisateurs.

- Autorisez l’évolutivité en déployant plusieurs appliances Cloud Connector dans un ou plusieurs sites PSTN.

- Autorisez la haute disponibilité en déployant plusieurs appliances Cloud Connector au sein d’un seul site PSTN.

Cette rubrique présente les sites PSTN. Pour plus d’informations sur la planification de vos sites PSTN, voir [Plan for Cloud Connector Edition PSTN sites](plan-for-cloud-connector-edition-pstn-sites.md).

Vous pouvez déployer les topologies Cloud Connector suivantes :

- Une appliance Cloud Connector Edition unique par site PSTN. Cette topologie est recommandée uniquement à des fins d’évaluation, car elle ne fournit pas de haute disponibilité.

- Plusieurs appliances Cloud Connector Edition par site PSTN pour fournir une haute disponibilité.

- Plusieurs sites PSTN avec plusieurs appliances Cloud Connector Edition pour fournir une évolutivité avec une haute disponibilité. Vous pouvez déployer jusqu’à 200 sites.

Lors de la planification de votre topologie, prenons en compte les considérations suivantes :

- Avec Cloud Connector 2.0 et les ultérieures, un site PSTN peut avoir jusqu’à 16 appliances Cloud Connector. Les versions précédentes peuvent prendre en charge jusqu’à quatre appliances par site.

- Il existe deux types de configurations matérielles testées avec Cloud Connector :

  - La version plus grande est capable de gérer de grands volumes d’appels simultanés et est prise en charge dans tous les types d’environnements de production.

  - La version plus petite est conçue pour s’exécuter sur du matériel bas de gamme et peut être utilisée à des fins d’évaluation ou pour des sites avec de faibles volumes d’appels. Si vous déployez une version plus petite de Cloud Connector, vous devez toujours tenir compte de la configuration matérielle requise pour la classe production (par exemple, les deux alimentations).

- Si vous avez Cloud Connector version 2.0 ou ultérieure et que vous déployez la configuration maximale de 16 appliances (avec un matériel plus important), votre site PSTN peut gérer jusqu’à 8 000 appels simultanés. Si vous déployez la version la plus petite, la limite prise en charge est de 800.

    Vous devez également dédier certaines appliances à la haute disponibilité. La recommandation minimale est qu’une appliance doit être réservée à la haute disponibilité.

  - Avec la version 2, si vous déployez une configuration 15+1, votre site PSTN peut gérer jusqu’à 7 500 appels simultanés.

  - Si vous avez une version antérieure et déployez la configuration maximale de 3 + 1 (avec un matériel plus important), votre site PSTN peut gérer jusqu’à 1 500 appels simultanés. Si vous déployez la version la plus petite, la limite prise en charge est de 150.

-  Si vous devez avoir plus d’appels par site PSTN, vous pouvez monter en charge en déployant des sites PSTN supplémentaires au même emplacement.

> [!NOTE]
> Sauf indication, les diagrammes et les exemples ci-dessous supposent l’utilisation de la version plus grande de Cloud Connector.

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>Appliance Cloud Connector unique au sein d’un seul site PSTN

Le diagramme suivant illustre une appliance Cloud Connector Edition unique au sein d’un seul site PSTN. Notez que Cloud Connector se compose de quatre machines vm installées sur un ordinateur hôte physique qui se trouve dans un réseau de périmètre à des fins de sécurité.

![Un Cloud Connector avec un site PSTN.](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>Plusieurs appliances Cloud Connector au sein d’un seul site PSTN

 Pour des raisons d’évolutivité et de haute disponibilité, vous pouvez choisir d’avoir plusieurs éditions Cloud Connector dans un seul site PSTN, comme illustré dans le diagramme suivant. Vous devez tenir compte des éléments suivants :

- Les appels sont répartis dans un ordre aléatoire entre les connecteurs Cloud dans un pool.

- À des fins de planification de la capacité, vous devez envisager la possibilité de gérer la charge si un ou plusieurs connecteurs Cloud sont mis hors connexion, en fonction des calculs suivants :

  - **Cases N+1.** Pour la version plus grande de Cloud Connector, les cases N+1 supportent 500 N appels simultanés avec une disponibilité de \* 99,8 %.

    Pour la version plus petite de Cloud Connector, les cases N+1 supportent 50 N appels simultanés avec une disponibilité de \* 99,8 %.

  - **N+2 zones.** Pour la version plus grande de Cloud Connector, les cases N+2 supportent 500 N appels simultanés avec une disponibilité de \* 99,9 %.

    Pour la version plus petite de Cloud Connector, les cases N+2 supportent 50 N appels simultanés avec une disponibilité de \* 99,9 %.

![Deux connecteurs cloud au sein d’un site PSTN.](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>Plusieurs sites PSTN avec un ou plusieurs connecteurs cloud par site

Vous pouvez également choisir d’avoir plusieurs sites PSTN avec une ou plusieurs éditions Cloud Connector dans chaque site. Si votre site PSTN atteint la limite d’appels simultanés, vous pouvez ajouter un autre site PSTN pour gérer la charge.

Plusieurs sites PSTN vous permettent également de fournir une connectivité aux passerelles les plus proches de vos utilisateurs. Par exemple, supposons que vous avez des passerelles PSTN à Seattle et Amsterdam. Vous pouvez déployer deux sites PSTN (un à Seattle, un à Amsterdam) et affecter des utilisateurs pour qu’ils utilisent le site PSTN le plus proche. Les utilisateurs de Seattle seront acheminés vers le site PSTN de Seattle et les passerelles, tandis que les utilisateurs d’Amsterdam seront acheminés vers le site PSTN d’Amsterdam et les passerelles :

![Cloud Connector Edition dans 2 sites PSTN.](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>Conditions requises pour le déploiement
<a name="BKMK_Requirements"> </a>

Avant de déployer Cloud Connector Edition, assurez-vous que vous avez les données suivantes pour votre environnement :

- **Pour l’ordinateur hôte -** Les ordinateurs VM Cloud Connector doivent être déployés sur du matériel dédié exécutant Windows Server 2012 R2 Datacenter Edition (anglais) avec le rôle Hyper-V activé.

    Pour les versions 2.0 et ultérieures, la carte réseau de l’ordinateur hôte liée au commutateur de réseau d’entreprise Skype Entreprise doit avoir une adresse IP configurée dans le même sous-réseau que les ordinateurs réseau d’entreprise Cloud Connector.

- Pour les versions 2.1 et ultérieures, l’appliance hôte .NET Framework la version 4.6.1 ou ultérieure.

- **Pour les machines virtuelles :** Image ISO Windows Server 2012 R2 (anglais) (.iso). La valeur ISO sera convertie en disques durs virtuels pour les machines virtuelles qui s’exécuteront Skype Entreprise Cloud Connector Edition.

- Le matériel nécessaire pour prendre en charge l’installation des 4 ordinateurs VM pour chaque édition Cloud Connector de votre déploiement. Les configurations suivantes sont recommandées :

  - Double processeur 64 bits, six cœurs (12 cœurs réels), 2,50 gigahertz (GHz) ou supérieur

  - 64 gigaoctets (Go) de RAM ECC

  - Quatre disques SAS de cache SAS de 6 Gbits/s de 600 Go (ou plus) de 10 000 RPM, configurés dans une configuration RAID 5

  - Trois cartes réseau à haut débit 1 Gbps RJ45

- Si vous choisissez de déployer la version plus petite de Cloud Connector Edition qui prend en charge jusqu’à 50 appels simultanés, vous aurez besoin du matériel suivant :

  - Intel i7 4790 quadruple cœur avec Intel 4600 Graphics (aucun graphique haut de gamme requis)

  - 32 Go DDR3-1600 non ECC

  - 2 : 1 To 7200RPM SATA III (6 Gbits/s) dans RAID 0

  - 2 : 1 Gbps Ethernet (RJ45)

- Si un serveur proxy est requis sur l’ordinateur hôte pour naviguer sur Internet, vous devez apporter les modifications de configuration suivantes :

  - Pour contourner le proxy, spécifiez les paramètres de proxy WinHTTP définies avec votre serveur proxy et une liste de contournement incluant « 192.168.213 \* ». réseau utilisé par vos services de gestion Cloud Connector Skype Entreprise sous-réseau d’entreprise tel que défini dans CloudConnector.ini fichier. Sinon, la connectivité de gestion échouera et empêchera le déploiement et la récupération automatique de Cloud Connector. Voici un exemple de commande de configuration winhttp : netsh winhttp set proxy « 10.10.10.175:8080 » bypass-list= » \* .local;1. \* ; 172.20. \* ;192.168.218. \* ' \<local\> « .

  - Spécifiez les paramètres proxy par ordinateur plutôt que par utilisateur. Dans le cas contraire, les téléchargements de Cloud Connector échoueront. Vous pouvez spécifier les paramètres proxy par ordinateur avec une modification du Registre ou avec le paramètre de stratégie de groupe comme suit :

  - **Registre :** HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet Settings] ProxySettingsPerUser dword: 00000000

  - **Stratégie de groupe :** Modèles d’administration Windows composants Internet Explorer : définir les paramètres proxy par \> \> ordinateur \> (et non par utilisateur)

- PBX/trunk qualifié ou SBC/passerelle qualifié (un minimum de deux passerelles est recommandé).

    Cloud Connector prend en charge les mêmes contrôleurs de frontière de session (SCS) certifiés pour les Skype Entreprise. Pour plus d’informations, [voir Infrastructure téléphonique pour Skype Entreprise](../../../SfbPartnerCertification/certification/infra-gateways.md).

- Un compte d’administrateur de serveur local avec des autorisations pour installer et configurer Hyper-V sur les serveurs hôtes. Le compte doit avoir des autorisations d’administrateur sur le serveur local sur lequel Hyper-V est installé et configuré.

- Pendant le déploiement, vous serez invité à créer un compte d’administrateur de domaine avec les autorisations pour créer et publier la topologie dans le domaine Cloud Connector.

- Les enregistrements DNS externes, qui sont définis dans le fichier CloudConnector.ini inclus dans le package d’installation :

  - Enregistrement DNS externe pour le service Edge d’accès du composant Edge ; par exemple, \<Domain Name\> ap. Vous avez besoin d’un enregistrement par site PSTN. Cet enregistrement doit contenir les adresses IP de tous les edges de ce site.

- Une Microsoft 365 ou une Office 365 avec tous les enregistrements DNS et SRV requis créés.

    > [!IMPORTANT]
    > Lorsque vous intégrez votre client à Cloud Connector Edition, l’utilisation du suffixe de domaine par défaut, .onmicrosoft.com, en tant que domaine SIP pour votre organisation n’est pas prise en charge. > vous ne pouvez pas utiliser sip.\<Domain Name\> comme nom de votre interface proxy d’accès Edge Cloud Connector, car cet enregistrement DNS est utilisé par les Microsoft 365 et Office 365.

- Un certificat pour le service Edge externe obtenu auprès d’une autorité de certification publique.

- Les règles de pare-feu permettant d’autoriser le trafic via les ports requis sont terminées.

- Une connexion Internet pour l’ordinateur hôte et les machines vm. Cloud Connector télécharge certains logiciels à partir d’Internet . par conséquent, vous devez fournir des informations sur la passerelle et le serveur DNS afin que l’ordinateur hôte cloud Connector et les ordinateurs VM se connectent à Internet et téléchargent les logiciels nécessaires.

- Module PowerShell distant client installé sur l’ordinateur hôte.

- Les informations Skype Entreprise’administrateur pour exécuter PowerShell à distance.

    > [!IMPORTANT]
    > L’authentification multifacteur NE DOIT PAS être activée sur le compte d’administrateur.

> [!NOTE]
> Le déploiement de Cloud Connector est uniquement pris en charge sur Microsoft Hyper-V plateforme virtualisée. Les autres plateformes, telles que VMware et Amazon Web Services, ne sont pas pris en charge.

> [!NOTE]
> Les instructions matérielles minimales pour exécuter Cloud Connector sont basées sur la capacité matérielle de base (cœurs, MHz, gigaoctets, etc.) avec une certaine mémoire tampon pour prendre en charge les baisses de performances invisibles dans l’architecture de n’importe quel ordinateur. Microsoft a exécuté le pire test de charge sur le matériel disponible sur le marché, en fonction des recommandations minimales. La qualité des médias et les performances du système sont vérifiées. Les partenaires officiels d’appliance Cloud Connector de Microsoft ont des implémentations matérielles Cloud Connector spécifiques sur lesquelles ils ont testé indépendamment les performances et ils respectent l’aptitude de leur matériel à répondre aux exigences de charge et de qualité.

> [!NOTE]
> Les appareils produits par AudioCodes et Sonus ont modifié le code et s’exécutent sur Windows server Standard edition de serveurs. Ces appareils sont pris en charge.

## <a name="information-you-need-to-gather-before-deployment"></a>Informations à collecter avant le déploiement
<a name="BKMK_PlanDeployment"> </a>

Avant de commencer votre déploiement, vous devez déterminer la taille de votre déploiement, les domaines SIP qui sont en cours de service et les informations de configuration pour chaque site PSTN que vous prévoyez de déployer. Pour commencer, vous devez :

- Identifiez tous les domaines SIP qui seront servis par ce déploiement en fonction des URL SIP en cours d’utilisation dans votre entreprise.

- Déterminez le nombre de sites PSTN à déployer.

- Assurez-vous que vous avez le matériel nécessaire pour prendre en charge les quatre ordinateurs VM que vous installerez pour chaque édition cloud Connector.

Pour chaque site PSTN que vous prévoyez de déployer, vous devez :

- Créez des noms pour tous les composants de chaque appliance Cloud Connector (voir [Déterminer les paramètres de déploiement).](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)

- Définir des plages de ports (voir [Ports et protocoles).](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)

- Créez des enregistrements DNS externes pour le composant Edge (voir [Conditions requises pour le déploiement).](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- Déterminez vos exigences en matière de certificats pour le composant Edge (voir [Exigences relatives aux certificats).](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)

### <a name="ports-and-protocols"></a>Ports et protocoles
<a name="BKMB_Ports"> </a>

Lorsque vous définissez des plages de ports multimédias, ez compte des éléments suivants :

- Les clients utilisent toujours la plage de ports 50000 à 50019 pour le trafic multimédia ; cette plage est prédéfinée dans Skype Entreprise Online et ne peut pas être modifiée.

- Par défaut, le composant de médiation utilise la plage de ports 49 152 à 57 500 pour le trafic multimédia. Toutefois, la connexion est établie via le pare-feu interne et, pour des raisons de sécurité, vous pouvez limiter cette plage de ports dans votre topologie. Vous aurez besoin de quatre ports au plus par appel. Si vous souhaitez limiter le nombre de ports entre le composant de médiation et la passerelle PSTN, vous devez également configurer la plage de ports correspondante sur la passerelle.

- Vous devez déployer Cloud Connector dans un réseau de périmètre. Cela signifie que vous aurez deux pare-feu :

  - Le premier pare-feu est externe entre Internet et votre réseau de périmètre.

  - Le deuxième pare-feu est interne entre le réseau de périmètre et votre réseau interne.

    Vos clients peuvent se trouver sur Internet ou sur le réseau interne :

  - Les clients sur Internet se connectent à votre réseau PSTN via le pare-feu externe via le composant Edge.

  - Les clients du réseau interne se connectent via le pare-feu interne au composant de médiation dans le réseau de périmètre, qui connectera le trafic à la passerelle SBC ou PSTN.

    Cela signifie que vous devez ouvrir des ports dans les deux pare-feu.

Les tableaux suivants décrivent les ports et les plages de ports pour les pare-feu externes et internes.

Ce tableau indique les ports et les plages de ports permettant d’activer la communication entre les clients dans le réseau interne et le composant de médiation :

**Pare-feu interne**



|**IP source**|**Adresse IP de destination**|**Port source**|**Port de destination**|
|:-----|:-----|:-----|:-----|
|Composant de médiation Cloud Connector  <br/> |Passerelle SBC/PSTN  <br/> |N’importe lequel  <br/> |TCP 5060\*\*  <br/> |
|Passerelle SBC/PSTN  <br/> |Composant de médiation Cloud Connector  <br/> |N’importe lequel  <br/> |TCP 5068/ TLS 5067  <br/> |
|Composant de médiation Cloud Connector  <br/> |Passerelle SBC/PSTN  <br/> |UDP 49 152 - 57 500  <br/> |Any\*\*\*  <br/> |
|Passerelle SBC/PSTN  <br/> |Composant de médiation Cloud Connector  <br/> |Any\*\*\*  <br/> |UDP 49 152 - 57 500  <br/> |
|Composant de médiation Cloud Connector  <br/> |Clients internes  <br/> |TCP 49 152 - 57 500\*  <br/> |TCP 50 000-50 019  <br/> (Facultatif)  <br/> |
|Composant de médiation Cloud Connector  <br/> |Clients internes  <br/> |UDP 49 152 - 57 500\*  <br/> |UDP 50 000-50 019  <br/> |
|Clients internes  <br/> |Composant de médiation Cloud Connector  <br/> |TCP 50 000-50 019  <br/> |TCP 49 152 - 57 500\*  <br/> |
|Clients internes  <br/> |Composant de médiation Cloud Connector  <br/> |UDP 50 000-50 019  <br/> |UDP 49 152 -57 500\*  <br/> |

\* Il s’agit de la plage de ports par défaut sur le composant de médiation. Pour un flux d’appels optimal, quatre ports par appel sont requis.

\*\* Ce port doit être configuré sur la passerelle SBC/PSTN . 5060 est un exemple. Vous pouvez configurer d’autres ports sur votre passerelle SBC/PSTN.

\*\*\* Notez que vous pouvez également limiter la plage de ports sur votre SBC/passerelle si le fabricant du SBC/passerelle l’a autorisé.

Pour des raisons de sécurité, vous pouvez limiter la plage de ports pour le composant de médiation à l’aide de l’cmdlet [Set-CsMediationServer.](/powershell/module/skype/set-csmediationserver?)

Par exemple, la commande suivante limite le nombre de ports que le composant de médiation utilisera pour le trafic multimédia à 50 000 - 51 000 pour l’audio (entrée et sortie). Le composant de médiation pourra gérer 250 appels simultanés avec cette configuration. Notez que vous pouvez également limiter cette plage sur la passerelle SBC/PSTN :

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

Pour récupérer le nom du composant de médiation et voir les ports par défaut, vous pouvez utiliser l’cmdlet [Get-CsService](/powershell/module/skype/get-csservice?) comme suit :

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

Le tableau suivant présente les ports et les plages de ports permettant d’activer la communication entre le composant Edge cloud Connector et le pare-feu externe. Ce tableau indique une recommandation minimale.

Dans ce cas, tout le trafic multimédia vers Internet se fera via le edge en ligne comme suit : Point de fin utilisateur -- Edge en ligne \> - Cloud Connector Edge \> :

**Pare-feu externe : configuration minimale**



|**IP source**|**Adresse IP de destination**|**Port source**|**Port de destination**|
|:-----|:-----|:-----|:-----|
|N’importe lequel  <br/> |Interface externe edge cloud connector  <br/> |N’importe lequel  <br/> |TCP(MTLS) 5061  <br/> |
|Interface externe edge cloud connector  <br/> |N’importe lequel  <br/> |N’importe lequel  <br/> |TCP(MTLS) 5061  <br/> |
|Interface externe edge cloud connector  <br/> |N’importe lequel  <br/> |N’importe lequel  <br/> |TCP 80  <br/> |
|Interface externe edge cloud connector  <br/> |N’importe lequel  <br/> |N’importe lequel  <br/> |UDP 53  <br/> |
|Interface externe edge cloud connector  <br/> |N’importe lequel  <br/> |N’importe lequel  <br/> |TCP 53  <br/> |
|Interface externe edge cloud connector  <br/> |N’importe lequel  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|N’importe lequel  <br/> |Interface externe edge cloud connector  <br/> |TCP 50 000-59 999  <br/> |TCP 443  <br/> |
|N’importe lequel  <br/> |Interface externe edge cloud connector  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Interface externe edge cloud connector  <br/> |N’importe lequel  <br/> |TCP 50 000-59 999  <br/> |TCP 443  <br/> |

Le tableau suivant présente les ports et les plages de ports permettant d’activer la communication entre le composant Edge cloud Connector et le pare-feu externe. Ce tableau indique la solution recommandée.

Dans ce cas, tout le trafic multimédia pour le point de fin sur Internet peut circuler directement vers le composant Edge cloud Connector. Le chemin d’accès au média sera Point de fin de l’utilisateur - \> Cloud Connector Edge.

> [!NOTE]
> Cette solution ne fonctionne pas si le point de fin de l’utilisateur se trouve derrière un NAT symétrique.

**Pare-feu externe : configuration recommandée**


|**IP source**|**Adresse IP de destination**|**Port source**|**Port de destination**|
|:-----|:-----|:-----|:-----|
|N’importe lequel  <br/> |Interface externe edge cloud connector  <br/> |N’importe lequel  <br/> |TCP(MTLS) 5061  <br/> |
|Interface externe edge cloud connector  <br/> |N’importe lequel  <br/> |N’importe lequel  <br/> |TCP(MTLS) 5061  <br/> |
|Interface externe edge cloud connector  <br/> |N’importe lequel  <br/> |N’importe lequel  <br/> |TCP 80  <br/> |
|Interface externe edge cloud connector  <br/> |N’importe lequel  <br/> |N’importe lequel  <br/> |UDP 53  <br/> |
|Interface externe edge cloud connector  <br/> |N’importe lequel  <br/> |N’importe lequel  <br/> |TCP 53  <br/> |
|Interface externe edge cloud connector  <br/> |N’importe lequel  <br/> |TCP 50 000-59 999  <br/> |N’importe lequel  <br/> |
|Interface externe edge cloud connector  <br/> |N’importe lequel  <br/> |UDP 3478; UDP 50 000-59 999  <br/> |N’importe lequel  <br/> |
|N’importe lequel  <br/> |Interface externe edge cloud connector  <br/> |N’importe lequel  <br/> |TCP 443 ; TCP 50 000-59 999  <br/> |
|N’importe lequel  <br/> |Interface externe edge cloud connector  <br/> |N’importe lequel  <br/> |UDP 3478; UDP 50 000 - 59 999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>Exigences de connectivité Internet de l’hôte
<a name="BKMB_Ports"> </a>

L’ordinateur hôte doit être en mesure d’atteindre des ressources externes pour installer, mettre à jour et gérer Correctement Cloud Connector. Le tableau suivant indique les destinations et ports requis entre l’ordinateur hôte et les ressources externes.

|Direction  <br/> |Adresse IP source  <br/> |Adresse IP de destination  <br/> |Port source  <br/> |Port de destination  <br/> |Protocole  <br/> |Objectif  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sortant  <br/> |IPS d’hôte Cloud Connector  <br/> |indifférent  <br/> |indifférent  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|Sortant  <br/> |IPS d’hôte Cloud Connector  <br/> |indifférent  <br/> |indifférent  <br/> |80, 443  <br/> |TCP  <br/> |Liste de révocation de certificats (CRL)  <br/> |
|Sortant  <br/> |IPS d’hôte Cloud Connector  <br/> |indifférent  <br/> |indifférent  <br/> |80, 443  <br/> |TCP  <br/> |Mise à jour de Cloud Connector  <br/> Skype Entreprise Online  <br/> Admin PowerShell  <br/> Windows Update  <br/> |

Si des règles plus restrictives sont requises, reportez-vous aux URL de listes d’adresses allowlist suivantes :

- [URL de liste de révocation de certificats](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) [dans Office 365 URL et plages d’adresses IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)

- Windows Mise à jour [: gérer les paramètres Windows de mise à jour](/windows/deployment/update/waas-wu-settings)

- Skype Entreprise Online Admin PowerShell : \* .online.lync.com

    Si vous avez besoin d’une exclusion de proxy pour cette destination, vous devez l’ajouter à la liste de contournement WinHTTP.

- Mise à jour de Cloud Connector [: Centre de](https://aka.ms/CloudConnectorInstaller)téléchargement [https://go.microsoft.com](https://go.microsoft.com) et [https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>Résolution de noms DNS pour le composant Edge
<a name="BKMB_Ports"> </a>

Le composant Edge doit résoudre les noms externes des services Microsoft 365 ou Office 365 et les noms internes d’autres composants Cloud Connector.

Chaque composant Edge est un ordinateur multi-accueil avec des interfaces externes et internes. Cloud Connector déploie des serveurs DNS sur le composant Contrôleur de domaine dans le réseau de périmètre. Vous pouvez pointer le serveur Edge vers le serveur DNS dans le périmètre pour toutes les résolutions de noms, mais vous devez activer le serveur DNS Cloud Connector pour résoudre les noms externes en setting a DNS zone containing one or more DNS A records for external queries that refer name lookups to other public DNS servers.

Dans le fichier .ini, si vous définissez le nom de domaine complet pour les passerelles à partir du même espace de domaine que votre domaine SIP, la zone faisant autorité pour ce domaine SIP sera créée dans le serveur DNS dans le périmètre. Si le serveur Edge pointe vers ce serveur DNS pour résoudre les noms, Edge ne résoudra jamais les _sipfederationtls.\<yourdomain\> Enregistrement DNS requis pour le flux d’appels. Dans ce cas, Microsoft recommande de fournir un serveur DNS sur l’interface externe Edge pour résoudre les listes de recherche de noms Internet, et chaque composant Edge doit utiliser un fichier HÔTE pour résoudre d’autres noms de composants Cloud Connector en adresses IP.

> [!NOTE]
> Pour des raisons de sécurité, nous vous recommandons de ne pas pointer le serveur DNS Cloud Connector vers des serveurs internes dans le domaine de production pour la résolution de noms.

### <a name="determine-deployment-parameters"></a>Déterminer les paramètres de déploiement
<a name="BKMK_SiteParams"> </a>

Vous devez d’abord définir les paramètres de déploiement courants suivants :


|**Item**|**Description**|**Notes**|
|:-----|:-----|:-----|
|Domaines SIP  <br/> |URI SIP utilisé par les utilisateurs de l’entreprise. Fournissez tous les domaines SIP qui seront servis par ce déploiement. Vous pouvez avoir plusieurs domaines SIP.  <br/> ||
|Nombre de sites PSTN  <br/> |Nombre de sites PSTN que vous allez déployer.  <br/> ||

Pour chaque site PSTN que vous prévoyez de déployer, vous devez collecter les informations suivantes avant de commencer le déploiement. Vous devrez fournir ces informations lorsque vous mettrez à jour CloudConnector.ini fichier.

Lors de la configuration des informations de passerelle, n’oubliez pas les points suivants :

- Si vous n’avez qu’une seule passerelle, supprimez la section du fichier .ini pour la deuxième passerelle. S’il existe plus de deux passerelles, suivez le format existant pour en ajouter de nouvelles.

- Assurez-vous que l’adresse IP et le port des passerelles sont corrects.

- Pour prendre en charge la ha au niveau de la passerelle PSTN, conservez la passerelle secondaire ou ajoutez des passerelles supplémentaires.

(Facultatif) Pour limiter les numéros d’appels sortants, mettez à jour la valeur LocalRoute.



|**Paramètres du site**|**Description**|**Notes**|
|:-----|:-----|:-----|
|Nom de domaine de la machine virtuelle  <br/> |Nom de domaine pour les composants internes de Cloud Connector. Ce domaine doit être différent du domaine de production. Le nom doit être le même pour toutes les appliances Cloud Connector.  <br/> Nom dans .ini fichier : « VirtualMachineDomain »  <br/> |Le domaine .local est préféré.  <br/> |
|Nom du contrôleur de domaine Cloud Connector  <br/> |Nom du contrôleur de domaine.  <br/> Nom dans .ini fichier : « ServerName »  <br/> |Doit comprendre au moins 15 caractères. Entrez le nom Netbios uniquement.  <br/> |
|Masque IP/sous-réseau du contrôleur de domaine Cloud Connector  <br/> |Adresse IP du contrôleur de domaine.  <br/> Nom dans .ini fichier : « IP »  <br/> ||
|Microsoft 365 ou Office 365 FQDN de service en ligne  <br/> |Doit être la valeur par défaut dans la plupart des cas pour la Microsoft 365 ou Office 365 instance.  <br/> Nom dans .ini fichier : « OnlineSipFederationFqdn »  <br/> ||
|SiteName  <br/> |Skype Entreprise site ; par exemple, Seattle.  <br/> Nom dans .ini fichier : « SiteName »  <br/> Pour la version 1.4.1 et les ultérieures, le nom du site doit être différent pour chaque site et le nom doit correspondre au site PSTN, s’il existe, défini dans Microsoft 365 ou Office 365. Notez que les sites PSTN sont automatiquement créés lors de l’inscription de la première appliance dans un site.  <br/> ||
|HardwareType  <br/> Version 1.4.1 et ultérieures  <br/> |Type de matériel. La valeur par défaut est Normal. Vous pouvez également définir sur Minimum.  <br/> ||
|Country Code  <br/> |Code pays pour la numérotation.  <br/> Nom dans .ini fichier : " CountryCode »  <br/> ||
|Ville  <br/> |Ville (facultatif).  <br/> Nom dans .ini fichier : « City »  <br/> ||
|État  <br/> |État (facultatif).  <br/> Nom dans .ini fichier : « State »  <br/> ||
|Adresse IP de la VM de base  <br/> |Adresse IP de la machine virtuelle de base temporaire qui sera utilisée pour créer le VHDX pour toutes les machines virtuelles Cloud Connector. Cette adresse IP doit se trouver dans le même sous-réseau de réseau d’entreprise de périmètre défini à l’étape suivante et nécessite un accès à Internet. Assurez-vous de définir la passerelle d’entreprise par défaut et le DNS routable vers Internet.  <br/> Nom dans .ini fichier : « BaseVMIP »  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> Version 1.4.1 et ultérieures  <br/> |Adresse du serveur Windows Server Update Services (WSUS), un serveur intranet pour héberger les mises à jour à partir de Microsoft Update.  <br/> Vous pouvez laisser vide si WSUS n’est pas nécessaire.  <br/> ||
|Masque de sous-réseau pour le réseau interne  <br/> |Cloud Connector configure un réseau IP pour la communication interne entre les composants Cloud Connector. Edge doit également être connecté à un autre sous-réseau qui autorise la connectivité Internet.  <br/> Nom dans .ini fichier : « CorpnetIPPrefixLength » sous « Parameters for a pool of VM network »  <br/> ||
|Masque de sous-réseau pour le réseau externe  <br/> |Pour le réseau externe du composant Edge.  <br/> Nom dans .ini fichier : « InternetIPPrefix » sous « Parameters for a pool of VM network »  <br/> ||
|Nom du commutateur pour le réseau interne  <br/> |Nom du commutateur qui sera utilisé pour le réseau Cloud Connector interne.  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nom dans .ini fichier : « CorpnetSwitchName » sous « Parameters for a pool of VM network »  <br/> ||
|Nom du commutateur pour le réseau externe  <br/> |Nom du commutateur qui sera utilisé pour le réseau Cloud Connector externe.  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nom dans .ini fichier : « InternetSwitchName » sous « Parameters for a pool of VM network »  <br/> ||
|Passerelle par défaut pour le réseau interne  <br/> |Cette passerelle doit fournir un accès à Internet (Internet nécessite également la définition du serveur DNS) et sera configurée sur les interfaces internes des composants Cloud Connector.  <br/> Nom dans .ini fichier : « CorpnetDefaultGateway » sous « Parameters for a pool of VM network »  <br/> ||
|Passerelle par défaut pour l’interface externe du composant Edge  <br/> |Sera configuré sur l’interface externe du composant Edge.  <br/> Nom dans .ini fichier : « InternetDefaultGateway » sous « Parameters for a pool of VM network »  <br/> ||
|Serveur DNS pour le réseau interne  <br/> |Sera configuré sur l’interface interne de la machine vm temporaire. Doit fournir une résolution de noms pour les noms Internet. Sans fournir de serveur DNS, la connexion Internet échoue et le déploiement ne se termine pas.  <br/> Nom dans .ini fichier : « CorpnetDNSIPAddress » sous « Parameters for a pool of VM network »  <br/> ||
|Serveur DNS pour l’interface externe du composant Edge  <br/> |Sera configuré sur l’interface externe de Edge.  <br/> Nom dans .ini fichier : « InternetDNSIPAddress » sous « Parameters for a pool of VM network »  <br/> ||
|Nom du commutateur de gestion  <br/> |Le commutateur de gestion est un commutateur temporaire qui sera créé automatiquement et qui sera utilisé pour la configuration de Cloud Connector pendant le déploiement. Il sera déconnecté automatiquement après le déploiement. Il doit s’agit d’un sous-réseau différent de tout autre réseau utilisé dans Cloud Connector.  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nom dans .ini fichier : « ManagementSwitchName » sous « Parameters for a pool of VM network »  <br/> ||
|Adresse/masque de sous-réseau de gestion  <br/> |Le sous-réseau de gestion est un sous-réseau temporaire qui sera créé automatiquement et qui sera utilisé pour la configuration de Cloud Connector pendant le déploiement. Il sera supprimé automatiquement après le déploiement. Il doit s’agit d’un sous-réseau différent de tout autre réseau utilisé dans Cloud Connector.  <br/> Noms dans .ini fichier : « ManagementIPPrefix » et « ManagementIPPrefixLength » sous « Parameters for a pool of VM network »  <br/> ||
|Ordinateur du magasin central de gestion (CMS)  <br/> |Un seul FQDN utilisé pour le magasin central de gestion (CMS). Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nom dans .ini fichier : « ServerName » sous « Parameters for Primary Central Management Service »  <br/> |Doit comprendre au moins 15 caractères. Entrez le nom Netbios uniquement.  <br/> (Nom du pool CMS = Nom du serveur)  <br/> |
|Adresse IP de l’ordinateur CMS  <br/> |Adresse IP du serveur CMS (interne dans le réseau de périmètre).  <br/> Nom dans le fichier INI : « IP » sous « Parameters for Primary Central Management Service »  <br/> ||
|Nom du partage de fichiers  <br/> |Nom de partage de fichiers à créer sur le serveur CMS pour Skype Entreprise de réplication de fichiers (par exemple, CmsFileStore).  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nom dans .ini fichier : « CmsFileStore » sous « Parameters for Primary Central Management Service »  <br/> ||
|Nom du pool du composant de médiation  <br/> |Nom du pool du composant de médiation. Entrez le nom Netbios uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nom dans .ini fichier : « PoolName » sous « Parameters for a pool of Mediation Servers »  <br/> |Doit comprendre au moins 15 caractères. Entrez le nom Netbios uniquement.  <br/> |
|Nom du composant de médiation  <br/> |Nom du composant de médiation 1. Entrez le nom Netbios uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nom dans .ini fichier : « ServerName » sous « Parameters for a pool of Mediation Servers »  <br/> |Doit comprendre au moins 15 caractères. Entrez le nom Netbios uniquement.  <br/> |
|Adresse IP de l’ordinateur du composant de médiation  <br/> |Adresse IP du réseau d’entreprise interne pour le composant de médiation (interne dans le réseau de périmètre).  <br/> Nom dans .ini fichier : « IP » sous « Parameters for a pool of Mediation Servers »  <br/> ||
|Nom interne du pool edge  <br/> |Nom du pool du composant Edge. Entrez le nom Netbios uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nom dans .ini fichier : « InternalPoolName » sous « Parameters for a pool of Edge Servers »  <br/> |Doit comprendre au moins 15 caractères. Entrez le nom Netbios uniquement.  <br/> |
|Nom interne du serveur Edge  <br/> |Nom du composant Edge. Entrez le nom Netbios uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nom dans .ini fichier : « InternalServerName » sous « Parameters for a pool of Edge Servers »  <br/> |Doit comprendre au moins 15 caractères. Entrez le nom Netbios uniquement.  <br/> |
|Adresse IP interne du serveur Edge  <br/> |Adresse IP du réseau de périmètre interne du composant Edge pour communiquer avec d’autres composants de Cloud Connector.  <br/> Nom dans .ini fichier : « InternalServerIPs » sous « Parameters for a pool of Edge Servers »  <br/> ||
|Nom externe du pool d’accès  <br/> |Nom du edge d’accès ; par exemple, AP. Ce nom doit correspondre au nom fourni pour le certificat SSL. Entrez le nom Netbios uniquement. Le nom de domaine SIP sera utilisé pour générer le nom de domaine complet. Un nom de pool externe sera utilisé pour tous les composants Edge du pool. Un pool d’accès Edge est requis par site PSTN.  <br/> Nom dans .ini fichier : « ExternalSIPPoolName » sous « Parameters for a pool of Edge Servers »  <br/> |Doit comprendre au moins 15 caractères. Entrez le nom Netbios uniquement.  <br/> « sip » est réservé et ne peut donc pas être utilisé comme nom.  <br/> Le nom de domaine complet généré doit correspondre au nom fourni pour le certificat SSL.  <br/> |
|ADRESSE IP externe du edge d’accès  <br/> |ADRESSE IP externe du composant Edge : ip publique si aucune traduction d’adresses réseau n’est disponible ou adresse IP traduite (spécifiez les deux adresses si elles sont mappées).  <br/> Nom dans .ini fichier : « ExternalSIPIPs » sous « Parameters for a pool of Edge Servers »  <br/> ||
|Nom du relais multimédia  <br/> |Nom du relais audio-vidéo multimédia Edge ; par exemple, MR. Un nom de pool externe sera utilisé pour tous les composants Edge d’un pool. Un pool de relais multimédia Edge est requis par site PSTN.  <br/> Nom dans .ini fichier : « ExternalMRFQDNPoolName » sous « Parameters for a pool of Edge Servers »  <br/> |Doit comprendre au moins 15 caractères. Entrez le nom Netbios uniquement.  <br/> |
|ADRESSE IP externe du edge du relais multimédia  <br/> |Actuellement, une seule adresse IP est prise en charge. Il s’agit donc de la même adresse IP que l’adresse Edge d’accès, publique ou mappée (spécifiez les deux adresses si elles sont mappées). Peut être la même adresse que l’adresse IP externe du composant Edge du edge d’accès. Notez que si Edge se trouve derrière nat, vous devez également spécifier la valeur pour le paramètre suivant.  <br/> Nom dans .ini fichier : « ExternalMRIPs » sous « Parameters for a pool of Edge Servers »  <br/> ||
|ADRESSE IP externe du edge du relais multimédia (si Edge se trouve derrière NAT)  <br/> |Si votre edge se trouve derrière nat, vous devez également spécifier l’adresse publique de l’appareil NAT.  <br/> Nom dans .ini fichier : « ExternalMRPublicIPs » sous « Parameters for a pool of Edge Servers »  <br/> ||
|Voice Gateway 1 Make and Model  <br/> |Spécifiez la make et le modèle de la passerelle SBC/Voice. Notez que vous pouvez connecter un appareil ou une trunk SIP à partir de la liste des périphériques testés sur [https://technet.Microsoft.com/UCOIP](../../../SfbPartnerCertification/certification/overview.md) .  <br/> ||
|Make and Model de Voice Gateway 2 (copiez cette ligne si vous avez plus de 2 passerelles)  <br/> |Spécifiez la make et le modèle de passerelle vocale. Notez que vous pouvez connecter un appareil à partir de la liste des périphériques testés sur [https://technet.Microsoft.com/UCOIP](../../../SfbPartnerCertification/certification/overview.md) .  <br/> ||
|Nom de la passerelle vocale 1  <br/> |Utilisé pour générer le nom de domaine (FQDN) de l’ordinateur avec le domaine AD. Obligatoire si TLS doit être utilisé entre le composant de médiation et la passerelle vocale. Si vous ne prévoyez pas d’utiliser le FQDN (par exemple, TLS n’est pas requis ou la passerelle vocale ne prend pas en charge la connexion à l’aide du FQDN (ip uniquement), spécifiez.  <br/> ||
|Nom de la passerelle vocale 2 (copiez cette ligne si vous avez plus de 2 passerelles)  <br/> |Utilisé pour générer le nom de domaine (FQDN) de l’ordinateur avec le domaine AD. Obligatoire si TLS doit être utilisé entre le composant de médiation et la passerelle vocale. Si vous ne prévoyez pas d’utiliser le FQDN (par exemple, TLS n’est pas requis ou la passerelle vocale ne prend pas en charge la connexion à l’aide du FQDN (ip uniquement), spécifiez.  <br/> ||
|Adresse IP de la passerelle vocale 1  <br/> |Adresse IP de la passerelle vocale.  <br/> ||
|Adresse IP de la passerelle vocale 2 (copiez cette ligne si vous avez plus de 2 passerelles)  <br/> |Adresse IP de la passerelle vocale.  <br/> ||
|Voice Gateway 1 Port # (copiez cette ligne si vous avez plus de 2 passerelles)  <br/> |Port sur le port sur le port d’écoute siP de la passerelle vocale, par exemple, 5060.  <br/> ||
|Voice Gateway 2 Port #  <br/> |Port sur le port sur le port d’écoute siP de la passerelle vocale, par exemple, 5060.  <br/> ||
|Protocole Voice Gateway 1 pour le trafic SIP  <br/> |TCP ou TLS.  <br/> ||
|Protocole Voice Gateway 2 pour le trafic SIP (copiez cette ligne si vous avez plus de 2 passerelles)  <br/> |TCP ou TLS.  <br/> ||
|Plage de ports de média externe pour le trafic vers et depuis le composant Edge  <br/> |Plage de ports TCP/UDP pour le trafic multimédia vers et depuis l’interface externe de Edge. Doit toujours commencer à 50 000. Pour plus d’informations, voir « Ports and Protocols ».  <br/> |50000 - 59 999  <br/> |
|Plage de ports multimédias pour communiquer avec le composant de médiation via le pare-feu interne  <br/> |Plage de ports UDP que le composant de médiation utilisera pour communiquer avec les clients et les passerelles (recommandation : 4 ports par appel).  <br/> ||
|Plage de ports multimédias pour communiquer avec/depuis Skype Entreprise client via un pare-feu interne  <br/> |À des fins de planification, ne peut pas être modifié. Les ports doivent être ouverts dans le pare-feu interne pour communiquer entre Skype Entreprise clients au sein du réseau interne et avec le composant de médiation.  <br/> |50 000- 50 019  <br/> |
|Mot de passe de certificat public  <br/> |Doit être fourni dans le script.  <br/> ||
|Coffre Mot de passe de l’administrateur du mode  <br/> Version 1.4.2 uniquement  <br/> |Coffre’administrateur en mode utilisateur pour le domaine Cc interne.  <br/> ||
|Mot de passe administrateur de domaine Cloud Connector  <br/> Version 1.4.2 uniquement  <br/> |Mot de passe de l’administrateur de domaine Cloud Connector (différent de votre domaine de production). Le nom d’utilisateur est Administrateur. Vous ne pouvez pas modifier le nom d’utilisateur.  <br/> ||
|Mot de passe administrateur des machines virtuelles  <br/> Version 1.4.2 uniquement  <br/> |Utilisé pour configurer le réseau de gestion pendant le déploiement.  <br/> Le nom d’utilisateur est Administrateur. Vous ne pouvez pas modifier le nom d’utilisateur.  <br/> ||
|CABackupFile  <br/> Version 2.0 et ultérieures  <br/> |Utilisé pour enregistrer le service d’autorité de certification du serveur Active Directory dans un fichier lors du déploiement de plusieurs appliances dans un site Cloud Connector. N’oubliez pas d’utiliser le même mot de passe pour toutes les appliances au sein d’un site Cloud Connector afin d’importer correctement le fichier de sauvegarde de l’ac dans la nouvelle appliance ajoutée.  <br/> ||
|CCEService  <br/> Version 2.0 et ultérieures  <br/> |Utilisé pour le service de gestion Cloud Connector ; doit accéder à l’annuaire de sites Cloud Connector. N’oubliez pas d’utiliser le même mot de passe pour toutes les appliances au sein d’un site Cloud Connector.  <br/> ||
|Microsoft 365 administrateur client Office 365 client  <br/> | Le compte est utilisé par Cloud Connector pour mettre à jour et gérer les paramètres du client pour Cloud Connector : <br/>  Version 2.0 et versions ultérieures : informations d’identification pour un compte Microsoft 365 ou un compte Office 365 avec des droits Skype Entreprise’administrateur. <br/>  Versions antérieures à la version 2.0 : informations d’identification pour un compte Microsoft 365 ou Office 365 avec des droits d’administrateur client global. <br/> ||
|Activer la prise en charge de REFER  <br/> |Cela permet de définir si la prise en charge SIP REFER est activée ou désactivée sur la configuration de la trunk sur votre IP/PBX. La valeur par défaut est True. Si votre passerelle IP/PBX prend en charge la prise en charge de REFER, laissez cette valeur sur True. Si ce n’est pas le cas, cette valeur doit être changée en False. Si vous ne savez pas si votre passerelle prend en charge REFER, voir [IP-PBXs et Passerelles qualifiées.](../../../SfbPartnerCertification/certification/infra-gateways.md)   <br/> ||
|EnableFastFailoverTimer  <br/> Version 2.0 et ultérieures  <br/> |Avec la valeur par défaut « True », si la passerelle ne répond pas aux appels sortants dans les 10 secondes, ils sont acheminés vers la passerelle disponible suivante . S’il n’existe aucune autre trunks, l’appel est automatiquement abandonné.  <br/> Toutefois, dans une organisation avec des réponses de passerelle et des réseaux lents, ou lorsque le processus d’établissement d’appels prend plus de 10 secondes, cela peut entraîner l’abandon inutile des appels.  <br/> Lorsque vous appelez certains pays, par exemple les Émirats arabes unis ou l’Irak, le processus d’établissement des appels peut prendre plus de 10 secondes. Vous devrez modifier la valeur sur False si vous rencontrez des problèmes similaires. N’oubliez pas de modifier le paramètre correspondant sur le SBC ou la passerelle connecté.  <br/> La valeur peut être True ou False. La valeur par défaut est True.  <br/> ||
|ForwardCallHistory  <br/> Version 2.0 et ultérieures  <br/> | Ce paramètre est utilisé pour activer les en-têtes SIP utilisés pour signaler l’appelant initial dans les scénarios de sonnerie simultanée, de transfert d’appel et de transfert d’appel. La définition du paramètre sur True activera deux en-têtes SIP : <br/>  History-Info <br/>  Referred-By <br/>  L’en-tête History-Info est utilisé pour le reciblage des demandes SIP et « fournit (s) un mécanisme standard pour capturer les informations de l’historique des demandes afin d’activer un large éventail de services pour les réseaux et les utilisateurs finaux » ([RFC 4244 - Section 1.1](http://www.ietf.org/rfc/rfc4244.txt)). Pour les interfaces de la connexion Cloud Connector, cela est utilisé dans les scénarios de sonnerie simultanée et de forwarding d’appel.  <br/>  La valeur peut être True ou False. La valeur par défaut est False. <br/> ||
|Pai avant  <br/> Version 2.0 et ultérieures  <br/> |PAI est une extension privée de SIP qui permet aux serveurs SIP de revendiquer l’identité des utilisateurs authentifiés. Pour le fournisseur de trunks SIP, PAI peut être utilisé à des fins de facture si les History-Info et Referred-By ne sont pas présents. Lorsque forward P-Asserted-Identity est activé dans la configuration, le serveur de médiation a pour effet de diriger les en-têtes PAI avec des URI SIP Tel de Cloud Connector vers la connexion &amp; SIP. Le serveur de médiation va forwarder les en-têtes PAI avec les numéros E.164 de l’URI tel reçus uniquement sur la connexion &amp; SIP vers Cloud Connector. Le serveur de médiation va également forwarder tous les en-têtes de confidentialité reçus dans les deux sens. Si la demande SIP envoyée par le serveur de médiation inclut un en-tête Confidentialité du formulaire - « Confidentialité : id » conjointement avec l’en-tête PAI, l’identité revendiquée doit rester privée en dehors du domaine d’confiance réseau.  <br/> La valeur peut être True ou False. La valeur par défaut est False.  <br/> ||

### <a name="certificate-requirements"></a>Spécifications des certificats
<a name="BKMK_Certs"> </a>

Chaque composant Edge nécessite un certificat d’une autorité de certification publique. Les certificats doivent avoir une clé privée exportable à copier entre les composants Edge. Pour répondre aux exigences de certificat, vous devez choisir entre les options suivantes et fournir le nom du sujet (SN) et l’autre nom de l’objet (SAN) pour le certificat.

 **Si vous avez un seul domaine SIP :**

- **Option 1.** Le nom de l’objet doit contenir le nom du pool que vous avez affecté aux composants Edge. Notez que le nom du sujet ne peut pas sip.sipdomain.com car ce nom est réservé au composant Edge Skype Entreprise en ligne. Le san doit contenir les sip.sipdomain.com et le nom du pool edge d’accès :

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **Option 2.** Si vous souhaitez utiliser un certificat générique unique sur tous les serveurs de pool de serveurs Edge que vous déployez, vous pouvez utiliser une entrée SAN générique de .sipdomain.com au lieu du nom du pool edge dans le \* certificat. Le nom du sujet peut être le nom du pool edge d’accès de l’un des pools edge que vous avez déployés :

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> Vous ne devez pas créer d’entrée DNS externe pour \<sipdomain\> sip. com, car ce nom appartient au Microsoft 365 ou Office 365 déploiement.

> [!NOTE]
> Si vous souhaitez utiliser un certificat unique pour tous les pools edge déployés dans votre organisation et que vous ne pouvez pas utiliser de certificat générique comme défini dans l’option 2, vous devez inclure le nom de domaine complet pour tous les pools Edge déployés dans le nom SAN du certificat.

 **Si vous avez plusieurs domaines SIP :**

Vous devez ajouter des sip.sipdomain.com pour chaque domaine SIP et le nom des pools Edge d’accès par domaine (il peut s’y trouver avec un pool physique mais avec des noms différents). Voici un exemple d’entrées SN et SAN dans un scénario de domaine sip multiple :

- **Option 1.** Le nom de l’objet doit contenir le nom du pool que vous avez affecté pour les composants Edge. Notez que le nom du sujet ne peut pas sip.sipdomain.com car ce nom est réservé au composant Edge Skype Entreprise en ligne. Le san doit contenir les sip.sipdomain.com et le nom du pool edge d’accès :

  ```console
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>Option 2.</strong> Si vous souhaitez utiliser un certificat générique unique sur tous les serveurs de pool de serveurs Edge que vous déployez, vous pouvez utiliser une entrée SAN générique de .sipdomain.com au lieu du nom du pool edge dans le \* certificat. Le nom du sujet peut être le nom du pool edge d’accès de l’un des pools edge que vous avez déployés :

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> Vous ne devez pas créer d’entrée DNS externe pour \<sipdomain\> sip. com, car ce nom appartient au Microsoft 365 ou Office 365 déploiement.

À des fins de déploiement, vous pouvez utiliser le tableau suivant :

|**Option**|**Description**|**Notes**|
|:-----|:-----|:-----|
|Quelle option utiliserez-vous pour votre déploiement ?  <br/> |Option 1 ou 2  <br/> ||
|SN  <br/> |Fournir le nom de service pour votre certificat  <br/> ||
|SAN  <br/> |Fournit le SAN pour votre certificat  <br/> ||

Si vous utilisez TLS entre la passerelle et le serveur de médiation, vous devez obtenir le certificat racine, ou chaîne de certificats complète, pour le certificat affecté à la passerelle.

## <a name="dial-plan-considerations"></a>Considérations sur le plan de numérotation
<a name="BKMK_DailPlan"> </a>

Cloud Connector nécessite l’utilisation d’un plan de numérotation en ligne. Pour plus d’informations sur la configuration d’un plan de numérotation en ligne, voir [Que sont les plans de numérotation ?](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>Considérations sur la haute disponibilité
<a name="BKMK_HA"> </a>

Lorsque vous déployez Cloud Connector Edition pour la haute disponibilité, vous déployez au moins deux appliances qui agissent comme une sauvegarde l’une pour l’autre. Chaque appliance se compose de quatre composants : Edge, médiation, magasin central de gestion (CMS) et contrôleur de domaine.

En règle générale, si un composant au sein d’une appliance est en panne, Cloud Connector Edition peut continuer à gérer les appels, mais vous devez prendre en compte les éléments suivants :

- **Considérations sur les composants de médiation, cms et contrôleur de domaine**

    Supposons que le composant CMS ou contrôleur de domaine d’une appliance soit en panne. L’appliance peut toujours gérer les appels entrants et sortants, mais si vous redémarrez un composant de médiation lorsque le contrôleur de domaine ou le composant CMS n’est pas accessible, la médiation ne fonctionne pas. Il en va de même pour le redémarrage du composant CMS lorsque le contrôleur de domaine est en panne.

    **Recommandation :** Avant de redémarrer les composants, vérifiez la disponibilité des autres composants de l’appliance.

- **Considérations sur les composants Edge**

    Si le composant Edge d’une appliance n’est pas disponible, le comportement des appels entrants et sortants diffère comme suit :

  - **Appel sortant :** appel de votre utilisateur sur Internet vers un réseau PSTN.

    Le mécanisme de distribution des appels dans le cloud identifiera qu’un composant Edge est en panne et routera tous les appels vers une autre appliance, afin que l’appel sortant réussisse.

  - **Appel entrant :** appel du réseau PSTN vers un utilisateur qui se trouve sur un réseau local ou sur Internet.

     Si le composant Edge de l’appliance qui a reçu l’appel ne fonctionne pas, les appels entrants vers cette appliance ne seront pas réussis, car le composant de médiation ne peut pas rediriger l’appel vers le composant Edge dans l’autre appliance.

    **Recommandation :** Mettre en place un système d’analyse. Après avoir identifié un dysfonctionnement du composant Edge, fermez tous les composants de l’appliance où le composant Edge n’est pas disponible.

## <a name="cloud-connector-media-flow"></a>Flux multimédia Cloud Connector
<a name="BKMK_MediaFlow"> </a>

Les diagrammes suivants décrivent le flux d’un appel sortant et entrant via Cloud Connector Edition. Il s’agit d’informations utiles pour comprendre comment la connectivité est établie.

Dans le premier diagramme, un utilisateur interne passe un appel sortant comme suit :

1. Dave, un utilisateur en ligne, mais maintenant sur le réseau interne, appelle un utilisateur PSTN externe.

2. Le trafic SIP a pour Skype Entreprise Online.

3. Skype Entreprise Online effectue une recherche inversée du numéro. La recherche de numéro inversée échoue, car ce numéro n’appartient à personne au Skype Entreprise organisation.

4. L’appel est d’abord acheminé vers le composant Edge (flux SIP et multimédia via Online Edge ; Le média est alors accessible au composant de médiation via le pare-feu interne.

5. Si l’itinéraire existe, le composant Edge relaie le trafic vers le composant de médiation dans le réseau de périmètre.

6. Le composant de médiation envoie le trafic vers la passerelle PSTN.

![Flux multimédia sortant pour Cloud Connector.](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

Dans le diagramme suivant, un utilisateur interne reçoit un appel entrant comme suit :

1. La passerelle PSTN reçoit un appel pour l’utilisateur Dave qui est en ligne, mais qui se trouve maintenant dans le réseau interne.

2. Le trafic SIP est acheminé vers le composant de médiation.

3. Le composant de médiation envoie le trafic SIP au composant Edge, puis il passe à Skype Entreprise Online.

4. Skype Entreprise Online effectue une recherche inversée du numéro et trouve qu’il s’agit de l’utilisateur Dave.

5. La signalisation SIP est envoyé à tous les points de présence de Dave.

6. Le trafic multimédia sera établi entre la passerelle et le composant de médiation et entre le composant de médiation et le point de fin.

![Support entrant Flow pour Cloud Connector.](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>Analyse et dépannage
<a name="BKMK_Monitor"> </a>

Le mécanisme de surveillance et de dépannage est installé automatiquement avec chaque appliance Cloud Connector. Le mécanisme détecte les événements suivants :

- Une ou plusieurs machines virtuelles d’une appliance Cloud Connector ne sont pas connectées à un commutateur virtuel interne ou Internet.

- Une ou plusieurs machines virtuelles d’une appliance Cloud Connector sont en état enregistré ou arrêté.

- Services qui ne sont pas en cours d’exécution.

  Si l’un des événements suivants est détecté, l’ensemble de l’appliance Cloud Connector est drainé et marqué comme hors connexion afin d’empêcher la tentative d’établir des appels à une appliance qui ne fonctionne pas correctement. Par la suite, les fonctionnalités de récupération automatique de Cloud Connector restaurent les services et marquent l’appliance comme étant en ligne. Si la récupération automatique échoue pour une raison quelconque, voir [Résoudre les problèmes de déploiement de Cloud Connector.](troubleshoot-your-cloud-connector-deployment.md)

  - Sur la machine virtuelle du magasin central de gestion :

     - Skype Entreprise Agent réplicateur maître

     - Skype Entreprise Agent réplicateur de réplicas

  - Sur la machine virtuelle du serveur de médiation :

     - Skype Entreprise Agent réplicateur de réplicas

     - Skype Entreprise Server Médiation

  - Sur la machine virtuelle du serveur Edge

     - Skype Entreprise Agent réplicateur de réplicas

     -  Skype Entreprise Server Edge d’accès

     - Skype Entreprise Server Edge audio/vidéo

     - Skype Entreprise Server Authentification audio/vidéo

     - Skype Entreprise Server Serveur Edge de conférence web

- Règle de trafic entrant Windows pare-feu pour « CS RTCSRV » sur Edge, « CS RTCMEDSRV » sur le serveur de médiation est désactivé.

Cloud Connector 2.1 et ultérieur prend en charge la surveillance de Cloud Connector à l’aide d’Operations Management Suite (OMS). Pour plus d’informations, voir [Surveiller Cloud Connector à l’aide d’Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

## <a name="for-more-information"></a>Pour plus d'informations
<a name="BKMK_MoreInfo"> </a>

Pour plus d'informations, consultez les articles suivants :

- [Détails sur les solutions téléphoniques Microsoft Telephony](/microsoftteams/cloud-voice-landing-page)

- [Configurer et gérer les Skype Entreprise Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md)

- [Planifier le contournement de média dans Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

- [Déployer le contournement de média dans Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)
