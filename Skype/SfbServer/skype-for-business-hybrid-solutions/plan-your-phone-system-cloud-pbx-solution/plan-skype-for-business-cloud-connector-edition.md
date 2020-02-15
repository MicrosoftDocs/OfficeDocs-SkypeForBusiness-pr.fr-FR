---
title: Planification de Skype entreprise, version Cloud Connector
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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6ce0e580-8c4a-45de-a54f-e39e438335d6
description: Trouvez des informations sur Skype entreprise, version Cloud Connector, un ensemble de machines virtuelles (VM) qui mettent en œuvre une connectivité RTC sur site avec le système téléphonique dans Office 365 (Cloud PBX).
ms.openlocfilehash: 9530fa2815dc491e6cda3579a801c3d5430f9b41
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018145"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Planification de Skype entreprise, version Cloud Connector

Trouvez des informations sur Skype entreprise, version Cloud Connector, un ensemble de machines virtuelles (VM) qui mettent en œuvre une connectivité RTC sur site avec le système téléphonique dans Office 365 (Cloud PBX).

La version de Cloud Connector peut être la bonne solution pour votre organisation si vous n’avez pas déjà un déploiement Lync Server ou Skype entreprise Server existant. Si vous recherchez toujours quel système téléphonique dans la solution Office 365 est approprié pour votre entreprise, consultez la rubrique [solutions de téléphonie Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions).

Ce document décrit la configuration requise pour la version Cloud Connector et les topologies prises en charge, et vous aide à planifier le déploiement de la version Cloud Connector. Veillez à lire cette rubrique avant de configurer votre environnement Cloud Connector. Lorsque vous êtes prêt à déployer et configurer la version Cloud Connector, reportez-vous à la rubrique [configure and Manage Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md).

La version 2,1 de Cloud Connector est désormais disponible. Si vous n’avez pas encore effectué la mise à niveau vers 2,1, consultez [la rubrique Upgrade to a New version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md). Vous trouverez le fichier d’installation à [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)l’adresse.

> [!NOTE]
> Microsoft prend en charge la version précédente de Cloud Connector Edition pendant 60 jours après la publication d’une nouvelle version. Microsoft prendra en charge la version 2.0.1 pendant 60 jours après la publication de 2,1 pour vous laisser le temps de mettre à niveau. Toutes les versions antérieures à 2.0.1 ne sont plus prises en charge.

La version Cloud Connector est une offre hybride composée d’un ensemble de machines virtuelles (VM) qui mettent en œuvre une connectivité RTC sur site avec le système téléphonique dans Office 365. En déployant une topologie Skype entreprise Server minimale dans un environnement virtualisé, les utilisateurs de votre organisation qui sont hébergés dans le Cloud peuvent recevoir des services PBX du Cloud Microsoft, mais la connectivité PSTN est fournie par le biais de la voix locale existante. architecture.

![Diagramme de topologie montrant la passerelle PBX Cloud Connecting Cloud PBX à un déploiement local de Skype entreprise.](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

Dans la mesure où Cloud Connector vous permet d’intégrer le système téléphonique dans les services Office 365 à votre environnement de téléphonie existant (par exemple, PBX, appareils analogiques et centres d’appels), vous pouvez implémenter une migration progressive de votre solution de téléphonie existante vers le téléphone. Système dans Office 365.

Par exemple, supposons que votre entreprise dispose d’un centre d’appels sophistiqué avec une fonctionnalité spécifique que le système téléphonique dans Office 365 ne fournit pas. Vous pouvez choisir de laisser les utilisateurs du centre d’appels avec la solution existante, mais déplacer les autres utilisateurs vers le système téléphonique dans Office 365.

Cloud Connector fournira le routage entre les utilisateurs hébergés sur site et en ligne, et vous pouvez choisir d’utiliser votre propre fournisseur PSTN avec le système téléphonique dans Office 365.

Tenez compte des éléments suivants lors de la planification du déploiement de Cloud Connector Edition :

- Pour utiliser Cloud Connector afin de tirer parti des solutions vocales Cloud, vous devez vous inscrire pour un client Office 365 qui inclut le système téléphonique dans Office 365. Si vous n’avez pas encore de client Office 365, vous pouvez apprendre à vous inscrire ici : [Office 365 pour les entreprises](https://products.office.com/business/office). Notez que vous devez vous inscrire pour obtenir un plan qui inclut Skype entreprise online.

- Pour enregistrer des appliances Cloud Connector avec le service Skype entreprise Online et pour exécuter différentes cmdlets, Cloud Connector 2,0 et versions ultérieures nécessite un compte Office 365 dédié avec les droits d’administrateur client Skype entreprise. Les versions de Cloud Connector antérieures à 2,0 requièrent un compte Office 365 dédié avec des droits d’administrateur général de client.

- Cloud Connector ne nécessite pas un déploiement complet de Skype entreprise Server.

    Actuellement, Cloud Connector ne peut pas coexister avec les serveurs locaux de Lync ou de Skype entreprise. Si vous souhaitez déplacer des utilisateurs Lync ou Skype entreprise existants vers Office 365 et continuer à fournir une téléphonie locale à vos utilisateurs, envisagez le système téléphonique dans Office 365 avec une connectivité locale à l’aide d’un déploiement Skype entreprise Server existant. Pour plus d’informations, reportez-vous à [la rubrique planification de votre système téléphonique dans office 365 (Cloud PBX) solution](plan-your-phone-system-cloud-pbx-solution.md) et [plan Phone system in Office 365 avec une connectivité RTC locale dans Skype entreprise Server](plan-phone-system-with-on-premises-pstn-connectivity.md).

- Si vous disposiez d’un déploiement Skype entreprise ou Lync Server précédent et que vous avez étendu le schéma, il n’est pas nécessaire de nettoyer le schéma pour le déploiement de Cloud Connector, tant que vous avez supprimé tous les composants Skype entreprise ou Lync Server de votre environnement.

- Vos utilisateurs sont hébergés en ligne.

- Si votre organisation a configuré la synchronisation d’annuaires (DirSync), tous les comptes des utilisateurs qui sont planifiés pour la voix hybride doivent d’abord être créés dans votre déploiement local, puis synchronisés avec le Cloud.

- Vous pouvez conserver votre opérateur RTC actuel si nécessaire.

- Si vous souhaitez fournir des conférences rendez-vous aux utilisateurs hébergés sur Cloud Connector, vous pouvez acheter une licence de conférence RTC ou payer pendant que vous offrez une offre de conférence audio auprès de Microsoft.

- La licence de conférence audio (ou offre de paiement à l’accès) est également requise pour les escalades d’appels. Si un utilisateur de Skype entreprise reçoit un appel d’un utilisateur RTC externe et souhaite ajouter un autre participant à cet appel (escalader l’appel vers une conférence), la remontée sera effectuée via le service d’audioconférence Microsoft.

- Cloud Connector 2,0 et les versions ultérieures prennent désormais en charge la déviation du trafic multimédia. La déviation du trafic multimédia permet à un client d’envoyer directement des médias au tronçon suivant du réseau téléphonique commuté (RTC), à savoir un contrôleur de frontière de session ou un contrôleur SBC (session Border Controller) et d’éliminer le composant Cloud Connector Edition du chemin de média. Pour plus d’informations, reportez-vous à la rubrique [plan for Media Bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).

- Cloud Connector 2,1 et versions ultérieures prend en charge la surveillance de Cloud Connector à l’aide d’Operations Management Suite (OMS). Pour plus d’informations, consultez la rubrique [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md) .

- Cloud Connector est disponible dans tous les pays où Office 365 entreprise E5 est disponible.

Cette rubrique comprend les sections suivantes :

- [Composants de Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [Topologies de la version Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [Configuration requise pour le déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [Informations que vous devez recueillir avant le déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [Considérations relatives au plan de numérotation](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [Considérations relatives à la haute disponibilité](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [Flux multimédia de Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [Analyse et dépannage](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [Pour plus d'informations](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>Composants de Cloud Connector
<a name="BKMK_Components"> </a>

Avec la version Cloud Connector, vous déployez un ensemble de machines virtuelles qui contiennent une topologie Skype entreprise Server minimale, constituée d’un composant Edge, d’un composant de médiation et d’un rôle de magasin central de gestion (CMS). Vous allez également installer un contrôleur de domaine, qui est requis pour le fonctionnement interne de Cloud Connector. Ces services sont configurés pour un environnement hybride avec votre client Office 365 qui inclut des services Skype entreprise online.

![Composants de Cloud Connector](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

Les composants de Cloud Connector offrent les fonctionnalités suivantes :

- **Composant Edge** : la communication entre la topologie locale et les services en ligne passe par le composant Edge, qui comprend les composants suivants :

  - **Accès Edge** : fournit un routage SIP entre le déploiement local et Skype entreprise online.

  - **Relais multimédia** : fournit le routage du trafic multimédia entre le composant de médiation et d’autres points de terminaison multimédia.

  - **Authentification du serveur relais multimédia/MRAS** : génère des jetons pour accéder au relais multimédia.

- **Routage sortant** : fournit un équilibrage de charge du trafic des communications vocales entre les passerelles ou les contrôleurs SBC connectés à une appliance Cloud Connector. Les appels seront répartis uniformément entre toutes les passerelles ou les contrôleurs SBC connectés à l’appliance Cloud Connector.

    Fournit le routage aux passerelles en fonction des stratégies. Seules les stratégies globales basées sur des numéros RTC de destination (sortant) sont prises en charge.

- **Rôle de magasin central de gestion (CMS)** : inclut le magasin de configurations pour les composants de topologie, y compris le transfert de fichiers CMS.

- **Réplica du magasin central de gestion** : synchronise les informations de configuration à partir de la base de données CMS globale sur le serveur de rôles CMS.

- **Contrôleur de domaine** -services de domaine Active Directory de Cloud Connector pour stocker tous les paramètres globaux et les groupes nécessaires au déploiement des composants de Cloud Connector. Une forêt est créée pour chaque appliance Cloud Connector. Le contrôleur de domaine ne doit pas avoir de connexions avec Active Directory de production. Les services Active Directory sont les suivants :

  - Services de domaine Active Directory

  - Services de certificats Active Directory pour émettre des certificats internes

- **Composant de médiation** : implémente le protocole de mappage SIP et de passerelle multimédia entre Skype entreprise et les passerelles RTC. Inclut un réplica CMS qui synchronise la configuration à partir de la base de données CMS globale.

## <a name="cloud-connector-edition-topologies"></a>Topologies de la version Cloud Connector
<a name="BKMK_Topologies"> </a>

Pour les besoins de cet article, nous allons faire référence aux sites PSTN. Un site RTC est une combinaison de plusieurs Appliances Cloud Connector déployées au même emplacement, avec des passerelles RTC communes connectées à ces appareils. Les sites RTC vous permettent d’effectuer les opérations suivantes :

- Fournir la connectivité aux passerelles les plus proches de vos utilisateurs.

- Autorisez l’extensibilité en déployant plusieurs Appliances Cloud Connector dans un ou plusieurs sites RTC.

- Autorisez la haute disponibilité en déployant plusieurs Appliances Cloud Connector sur un seul site RTC.

Cette rubrique présente les sites RTC. Pour plus d’informations sur la planification de vos sites RTC, reportez-vous à la rubrique [plan for Cloud Connector Edition PSTN sites](plan-for-cloud-connector-edition-pstn-sites.md).

Vous pouvez déployer les topologies de Cloud Connector suivantes :

- Une seule Appliance Cloud Connector par site RTC. Cette topologie est recommandée à des fins d’évaluation uniquement car elle ne fournit pas de haute disponibilité.

- Plusieurs Appliances Cloud Connector par site PSTN pour fournir une haute disponibilité.

- Plusieurs sites RTC avec plusieurs Appliances Cloud Connector pour assurer une évolutivité avec une haute disponibilité. Vous pouvez déployer jusqu’à 200 sites.

Lors de la planification de votre topologie, prenez en compte les éléments suivants :

- Avec Cloud Connector 2,0 et versions ultérieures, un site RTC peut avoir jusqu’à 16 Appliances Cloud Connector. Les versions précédentes prennent en charge jusqu’à 4 Appliances par site.

- Il existe deux types de configurations matérielles testées avec Cloud Connector :

  - La plus grande version est capable de gérer de grands volumes d’appels simultanés et est prise en charge dans tous les types d’environnements de production.

  - La version réduite est conçue pour s’exécuter sur du matériel de bas de gamme et peut être utilisée à des fins d’évaluation ou pour des sites avec des volumes d’appels faibles. Si vous déployez une version réduite de Cloud Connector, vous devez toujours prendre en compte les configurations matérielles de classe de production requises (comme les alimentations doubles).

- Si vous disposez de la version 2,0 de Cloud Connector ou d’une version ultérieure et que vous déployez la configuration maximale de 16 Appliances (avec un matériel plus important), votre site PSTN peut gérer jusqu’à 8 000 appels simultanés. Si vous déployez la version réduite, la limite prise en charge est de 800.

    Vous devez également dédier certaines appliances à la haute disponibilité. La recommandation minimale est qu’une appliance doit être réservée pour la haute disponibilité.

  - Avec la version 2, si vous déployez une configuration 15 + 1, votre site PSTN peut gérer jusqu’à 7 500 appels simultanés.

  - Si vous disposez d’une version antérieure et que vous déployez la configuration maximale 3 + 1 (avec du matériel plus important), votre site PSTN peut gérer jusqu’à 1500 appels simultanés. Si vous déployez la version réduite, la limite prise en charge est de 150.

-  Si vous avez besoin de davantage d’appels par site PSTN, vous pouvez monter en charge en déployant des sites PSTN supplémentaires au même emplacement.

> [!NOTE]
> Sauf indication contraire, les diagrammes et exemples ci-dessous supposent l’utilisation de la plus grande version de Cloud Connector.

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>Appliance Cloud Connector unique dans un site RTC unique

Le diagramme suivant illustre une seule Appliance Cloud Connector Edition dans un seul site RTC. Notez que Cloud Connector se compose de quatre machines virtuelles installées sur un ordinateur hôte physique qui se trouve dans un réseau de périmètre à des fins de sécurité.

![Un seul Cloud Connector avec un site RTC](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>Plusieurs Appliances Cloud Connector dans un site RTC unique

 Pour des raisons d’évolutivité et de haute disponibilité, vous pouvez choisir d’avoir plusieurs éditions Cloud Connector dans un site RTC unique, comme illustré dans le diagramme suivant. Vous devez tenir compte des éléments suivants :

- Les appels sont distribués dans un ordre aléatoire entre les connecteurs Cloud dans un pool.

- À des fins de planification de la capacité, vous devez envisager la possibilité de gérer la charge si un ou plusieurs connecteurs Cloud passent en mode hors connexion, en fonction des calculs suivants :

  - **Cases N + 1.** Pour la plus grande version de Cloud Connector, les cases N + 1\*prennent en charge 500 N appels simultanés avec une disponibilité de 99,8%.

    Pour la version réduite de Cloud Connector, les cases N + 1 prennent\*en charge 50 N appels simultanés avec une disponibilité de 99,8%.

  - **Cases N + 2.** Pour la plus grande version de Cloud Connector, les cases N + 2\*prennent en charge 500 N appels simultanés avec une disponibilité de 99,9%.

    Pour la version réduite de Cloud Connector, les cases N + 2 prennent\*en charge 50 N appels simultanés avec une disponibilité de 99,9%.

![Deux connecteurs Cloud dans un site RTC](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>Plusieurs sites RTC avec un ou plusieurs connecteurs Cloud pour chaque site

Vous pouvez également choisir d’avoir plusieurs sites RTC avec une ou plusieurs éditions de Cloud Connector dans chaque site. Si votre site RTC atteint la limite d’appels simultanés, vous pouvez ajouter un autre site PSTN pour gérer la charge.

Plusieurs sites RTC vous permettent également de fournir une connectivité aux passerelles les plus proches de vos utilisateurs. Par exemple, supposons que vous avez des passerelles PSTN à Seattle et Amsterdam. Vous pouvez déployer deux sites PSTN, l’un à Seattle, l’autre à Amsterdam, et affecter des utilisateurs pour utiliser le site PSTN le plus proche. Les utilisateurs de Seattle seront acheminés vers le site RTC et les passerelles de Seattle, tandis que les utilisateurs d’Amsterdam seront acheminés vers le site RTC et les passerelles d’Amsterdam :

![Version Cloud Connector dans 2 sites RTC](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>Configuration requise pour le déploiement
<a name="BKMK_Requirements"> </a>

Avant de déployer la version Cloud Connector, vérifiez que vous disposez des éléments suivants pour votre environnement :

- **Pour l’ordinateur hôte-** Les machines virtuelles de Cloud Connector doivent être déployées sur du matériel dédié exécutant Windows Server 2012 R2 Datacenter Edition (anglais) avec le rôle Hyper-V activé.

    Pour la version 2,0 et les versions ultérieures, la carte réseau de l’ordinateur hôte liée au commutateur de Skype entreprise corpnet doit avoir une adresse IP configurée dans le même sous-réseau que les ordinateurs du réseau d’entreprise Cloud Connector.

- Pour les versions 2,1 et ultérieures, .NET Framework 4.6.1 ou une version ultérieure doit être installé sur l’appareil hôte.

- **Pour les machines virtuelles-** Image Windows Server 2012 R2 ISO (en anglais) (. ISO). L’ISO sera convertie en disques durs virtuels pour les machines virtuelles qui exécuteront Skype entreprise, version Cloud Connector.

- Le matériel nécessaire pour prendre en charge l’installation des 4 machines virtuelles pour chaque édition de Cloud Connector dans votre déploiement. Les configurations suivantes sont recommandées :

  - Double processeur 64 bits, six cœurs (12 cœurs), 2,50 gigahertz (GHz) ou supérieur

  - 64 gigaoctets (Go) de RAM ECC

  - 4 600 Go (ou supérieur) 10 000 tr/min 128M disques SAS 6Gbps de cache, configurés dans une configuration RAID 5

  - Trois cartes réseau de 1 Gbits/s RJ45 à haut débit

- Si vous choisissez de déployer la version réduite de Cloud Connector Edition qui prend en charge jusqu’à 50 appels simultanés, vous aurez besoin du matériel suivant :

  - Intel i7 4790 quadruple cœur avec carte graphique Intel 4600 (aucune carte graphique haut de gamme nécessaire)

  - 32 Go non-ECC GDDR3-1600

  - 2:1 to 7200 TPM III (6 Gbits/s) en RAID 0

  - 2:1 Gbits/s Ethernet (RJ45)

- Si un serveur proxy est requis sur l’ordinateur hôte pour la navigation sur Internet, vous devez effectuer les modifications de configuration suivantes :

  - Pour contourner le proxy, spécifiez les paramètres de proxy WinHTTP définis avec votre serveur proxy et une liste de contournement incluant le «192.168.213. \*«réseau utilisé par les services de gestion de Cloud Connector et le sous-réseau de Skype entreprise corpnet tel que défini dans votre fichier CloudConnector. ini. Dans le cas contraire, la connectivité de gestion échoue et empêche le déploiement et la récupération automatique de Cloud Connector. Voici un exemple de commande de configuration WinHTTP : netsh WinHTTP Set proxy "10.10.10.175:8080" Bypass-List = "\*. local ; 1. \*; 172,20. \*; 192.168.218. \*«\<local\>».

  - Spécifiez les paramètres de proxy par ordinateur et non par utilisateur. Sinon, les téléchargements Cloud Connector échouent. Vous pouvez spécifier les paramètres de proxy par ordinateur à l’aide d’une modification du registre ou du paramètre de stratégie de groupe comme suit :

  - **Registre :** Paramètres de la HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet] ProxySettingsPerUser DWORD : 00000000

  - **Stratégie de groupe :** Modèles\>\>d’administration ordinateur composants\> Windows Internet Explorer : paramètres de proxy par ordinateur (plutôt que par utilisateur)

- PBX/jonction ou liaison SBC/passerelle qualifiée (un minimum de deux passerelles est recommandé).

    Cloud Connector prend en charge les mêmes contrôleurs de frontière de session (SBC) certifiés pour Skype entreprise. Pour plus d’informations, consultez la rubrique [infrastructure de téléphonie pour Skype entreprise](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

- Un compte d’administrateur de serveur local avec des autorisations pour installer et configurer Hyper-V sur les serveurs hôtes. Le compte doit disposer d’autorisations d’administrateur sur le serveur local sur lequel Hyper-V est installé et configuré.

- Pendant le déploiement, vous serez invité à créer un compte d’administrateur de domaine avec les autorisations nécessaires pour créer et publier la topologie dans le domaine Cloud Connector.

- Les enregistrements DNS externes, qui sont définis dans le fichier CloudConnector. ini inclus dans le package d’installation :

  - Enregistrement DNS externe pour le service Edge d’accès du composant Edge ; par exemple, AP.\<Domain Name\>. Vous avez besoin d’un enregistrement par site RTC. Cet enregistrement doit contenir les adresses IP de tous les Edges de ce site.

- Un client Office 365 avec tous les enregistrements DNS et SRV requis créés.

    > [!IMPORTANT]
    > Lorsque vous intégrez votre client à Cloud Connector Edition, l’utilisation du suffixe de domaine par défaut,. onmicrosoft.com, en tant que domaine SIP pour votre organisation, n’est pas prise en charge. > vous ne pouvez pas utiliser SIP. \<Nom\> de domaine en tant que nom de votre interface de proxy d’accès Edge de Cloud Connector car cet enregistrement DNS est utilisé par Office 365.

- Un certificat pour le serveur Edge externe obtenu auprès d’une autorité de certification publique (CA).

- Des règles de pare-feu pour autoriser le trafic via les ports requis ont été effectuées.

- Une connexion Internet pour l’ordinateur hôte et les machines virtuelles. Cloud Connector télécharge certains logiciels à partir d’Internet ; par conséquent, vous devez fournir des informations relatives à la passerelle et au serveur DNS de sorte que la machine hôte de Cloud Connector et les machines virtuelles puissent se connecter à Internet et télécharger les logiciels nécessaires.

- Un module client PowerShell distant installé sur l’ordinateur hôte.

- Les informations d’identification de l’administrateur Office 365 Skype entreprise pour exécuter PowerShell à distance.

    > [!IMPORTANT]
    > L’authentification multifacteur ne doit pas être activée pour le compte administrateur.

> [!NOTE]
> Le déploiement de Cloud Connector est uniquement pris en charge sur la plateforme virtualisée Microsoft Hyper-V. D’autres plateformes, telles que VMware et Amazon Web services, ne sont pas prises en charge.

> [!NOTE]
> Le guide matériel minimal pour exécuter Cloud Connector est basé sur une capacité matérielle de base (cœurs, MHz, gigaoctets, etc.) avec une mémoire tampon permettant de gérer des problèmes de performances imtangibles, enfouis dans l’architecture de n’importe quel ordinateur. Microsoft a exécuté le test de charge de cas le plus défavorable sur du matériel disponible dans le commerce pour répondre aux recommandations minimales. La qualité des médias et les performances du système sont vérifiées. Les partenaires de Microsoft officiels du service Cloud Connector ont des implémentations matérielles spécifiques de Cloud Connector sur lesquelles ils ont des performances testées de manière indépendante et ils sont en conformité avec leur matériel pour répondre aux exigences de charge et de qualité.

> [!NOTE]
> Les appareils produits par AudioCodes et Sonus ont modifié le code et s’exécutent sur Windows Server Standard Edition de serveurs. Ces appareils sont pris en charge.

## <a name="information-you-need-to-gather-before-deployment"></a>Informations que vous devez recueillir avant le déploiement
<a name="BKMK_PlanDeployment"> </a>

Avant de commencer votre déploiement, vous devez déterminer la taille de votre déploiement, les domaines SIP en cours de maintenance et les informations de configuration pour chaque site RTC que vous envisagez de déployer. Pour commencer, vous devez :

- Identifiez tous les domaines SIP qui seront pris en charge par ce déploiement en fonction des URI SIP utilisés dans votre entreprise.

- Déterminez le nombre de sites RTC que vous devez déployer.

- Assurez-vous que vous disposez du matériel nécessaire pour prendre en charge les quatre machines virtuelles que vous allez installer pour chaque édition de Cloud Connector.

Pour chaque site RTC que vous envisagez de déployer, vous devez :

- Créez des noms pour tous les composants de chaque équipement Cloud Connector (voir [determine Deployment Parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)).

- Définissez des plages de ports (voir [ports and Protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)).

- Créer des enregistrements DNS externes pour le composant Edge (voir [Configuration requise pour le déploiement](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)).

- Déterminez vos exigences en matière de certificats pour le composant Edge (voir [Certificate Requirements](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)).

### <a name="ports-and-protocols"></a>Ports et protocoles
<a name="BKMB_Ports"> </a>

Lors de la définition des plages de ports multimédias, gardez les points suivants à l’esprit :

- Les clients utilisent toujours la plage de ports 50000 à 50019 pour le trafic multimédia — cette plage est prédéfinie dans Skype entreprise Online et ne peut pas être modifiée.

- Le composant de médiation utilise par défaut la plage de ports 49 152 à 57 500 pour le trafic multimédia. Toutefois, la connexion est établie via un pare-feu interne et, pour des raisons de sécurité, vous pouvez limiter cette plage de ports dans votre topologie. Vous aurez besoin de 4 ports par appel. Si vous souhaitez limiter le nombre de ports entre le composant de médiation et la passerelle PSTN, vous devez également configurer la plage de ports correspondante sur la passerelle.

- Vous devez déployer Cloud Connector dans un réseau de périmètre. Cela signifie que vous aurez deux pare-feu :

  - Le premier pare-feu est externe entre Internet et votre réseau de périmètre.

  - Le deuxième pare-feu est interne entre le réseau de périmètre et votre réseau interne.

    Vos clients peuvent se trouver sur Internet ou sur le réseau interne :

  - Les clients sur Internet se connectent à votre réseau téléphonique commuté via le pare-feu externe via le composant Edge.

  - Les clients sur le réseau interne se connectent via le pare-feu interne au composant de médiation dans le réseau de périmètre, qui se connecte au trafic vers la passerelle SBC ou PSTN.

    Cela signifie que vous devez ouvrir des ports dans les deux pare-feu.

Les tableaux suivants décrivent les ports et les plages de ports pour les pare-feu externe et interne.

Ce tableau indique les ports et les plages de ports permettant la communication entre les clients dans le réseau interne et le composant de médiation :

**Pare-feu interne**



|**IP source**|**Adresse IP de destination**|**Port source**|**Port de destination**|
|:-----|:-----|:-----|:-----|
|Composant de médiation Cloud Connector  <br/> |Passerelle SBC/PSTN  <br/> |N'importe lequel  <br/> |TCP 5060\*\*  <br/> |
|Passerelle SBC/PSTN  <br/> |Composant de médiation Cloud Connector  <br/> |N'importe lequel  <br/> |TCP 5068/TLS 5067  <br/> |
|Composant de médiation Cloud Connector  <br/> |Passerelle SBC/PSTN  <br/> |UDP 49 152-57 500  <br/> |Chaque\*\*\*  <br/> |
|Passerelle SBC/PSTN  <br/> |Composant de médiation Cloud Connector  <br/> |Chaque\*\*\*  <br/> |UDP 49 152-57 500  <br/> |
|Composant de médiation Cloud Connector  <br/> |Clients internes  <br/> |TCP 49 152-57 500\*  <br/> |TCP 50000-50 019  <br/> Module  <br/> |
|Composant de médiation Cloud Connector  <br/> |Clients internes  <br/> |UDP 49 152-57 500\*  <br/> |UDP 50000-50 019  <br/> |
|Clients internes  <br/> |Composant de médiation Cloud Connector  <br/> |TCP 50000-50 019  <br/> |TCP 49 152-57 500\*  <br/> |
|Clients internes  <br/> |Composant de médiation Cloud Connector  <br/> |UDP 50000-50 019  <br/> |UDP 49 152-57 500\*  <br/> |

\*Il s’agit de la plage de ports par défaut sur le composant de médiation. Pour un flux d’appels optimal, quatre ports par appel sont nécessaires.

\*\*Ce port doit être configuré sur la passerelle SBC/PSTN ; 5060 est un exemple. Vous pouvez configurer d’autres ports sur votre passerelle SBC/PSTN.

\*\*\*Notez que vous pouvez également limiter la plage de ports sur votre SBC/passerelle si cela est autorisé par le fabricant de l’SBC/de la passerelle.

Pour des raisons de sécurité, vous pouvez limiter la plage de ports pour le composant de médiation à l’aide de la cmdlet [Set-applet csmediationserver](https://docs.microsoft.com/powershell/module/skype/set-csmediationserver?view=skype-ps) .

Par exemple, la commande suivante limite le nombre de ports utilisés par le composant de médiation pour le trafic multimédia vers 50 000-51 000 pour l’audio (entrée et sortie). Le composant de médiation pourra gérer les appels simultanés 250 avec cette configuration. Notez que vous pouvez également limiter cette plage sur la passerelle SBC/PSTN :

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

Pour récupérer le nom du composant de médiation et afficher les ports par défaut, vous pouvez utiliser la cmdlet [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps) comme suit :

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

Le tableau suivant indique les ports et les plages de ports permettant la communication entre le composant Edge de Cloud Connector et le pare-feu externe. Le tableau suivant présente une recommandation minimale.

Dans ce cas, tout le trafic multimédia vers Internet passe par le serveur Edge en ligne comme suit : point de terminaison utilisateur\>--Online Edge\>--Cloud Connector Edge :

**Pare-feu externe-configuration minimale**



|**IP source**|**Adresse IP de destination**|**Port source**|**Port de destination**|
|:-----|:-----|:-----|:-----|
|N'importe lequel  <br/> |Interface externe du serveur Edge de Cloud Connector  <br/> |N'importe lequel  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externe du serveur Edge de Cloud Connector  <br/> |N'importe lequel  <br/> |N'importe lequel  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externe du serveur Edge de Cloud Connector  <br/> |N'importe lequel  <br/> |N'importe lequel  <br/> |TCP 80  <br/> |
|Interface externe du serveur Edge de Cloud Connector  <br/> |N'importe lequel  <br/> |N'importe lequel  <br/> |UDP 53  <br/> |
|Interface externe du serveur Edge de Cloud Connector  <br/> |N'importe lequel  <br/> |N'importe lequel  <br/> |TCP 53  <br/> |
|Interface externe du serveur Edge de Cloud Connector  <br/> |N'importe lequel  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|N'importe lequel  <br/> |Interface externe du serveur Edge de Cloud Connector  <br/> |TCP 50000-000-59 999  <br/> |TCP 443  <br/> |
|N'importe lequel  <br/> |Interface externe du serveur Edge de Cloud Connector  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Interface externe du serveur Edge de Cloud Connector  <br/> |N'importe lequel  <br/> |TCP 50000-000-59 999  <br/> |TCP 443  <br/> |

Le tableau suivant indique les ports et les plages de ports permettant la communication entre le composant Edge de Cloud Connector et le pare-feu externe. Ce tableau indique la solution recommandée.

Dans ce cas, tout le trafic multimédia pour le point de terminaison sur Internet peut circuler directement vers le composant Edge de Cloud Connector. Le chemin d’accès aux médias est le point\> de terminaison utilisateur-serveur Edge de Cloud Connector.

> [!NOTE]
> Cette solution ne fonctionne pas si le point de terminaison de l’utilisateur se trouve derrière un NAT symétrique.

**Pare-feu externe-configuration recommandée**


|**IP source**|**Adresse IP de destination**|**Port source**|**Port de destination**|
|:-----|:-----|:-----|:-----|
|N'importe lequel  <br/> |Interface externe du serveur Edge de Cloud Connector  <br/> |N'importe lequel  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externe du serveur Edge de Cloud Connector  <br/> |N'importe lequel  <br/> |N'importe lequel  <br/> |TCP (MTLS) 5061  <br/> |
|Interface externe du serveur Edge de Cloud Connector  <br/> |N'importe lequel  <br/> |N'importe lequel  <br/> |TCP 80  <br/> |
|Interface externe du serveur Edge de Cloud Connector  <br/> |N'importe lequel  <br/> |N'importe lequel  <br/> |UDP 53  <br/> |
|Interface externe du serveur Edge de Cloud Connector  <br/> |N'importe lequel  <br/> |N'importe lequel  <br/> |TCP 53  <br/> |
|Interface externe du serveur Edge de Cloud Connector  <br/> |N'importe lequel  <br/> |TCP 50000-000-59 999  <br/> |N'importe lequel  <br/> |
|Interface externe du serveur Edge de Cloud Connector  <br/> |N'importe lequel  <br/> |UDP 3478 ; UDP 50000-000-59 999  <br/> |N'importe lequel  <br/> |
|N'importe lequel  <br/> |Interface externe du serveur Edge de Cloud Connector  <br/> |N'importe lequel  <br/> |TCP 443 ; TCP 50000-000-59 999  <br/> |
|N'importe lequel  <br/> |Interface externe du serveur Edge de Cloud Connector  <br/> |N'importe lequel  <br/> |UDP 3478 ; UDP 50 000-59 999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>Configuration requise pour la connectivité Internet hôte
<a name="BKMB_Ports"> </a>

L’ordinateur hôte doit être en mesure de joindre des ressources externes pour installer, mettre à jour et gérer correctement Cloud Connector. Le tableau suivant indique les destinations et les ports requis entre l’ordinateur hôte et les ressources externes.

|Direction  <br/> |Adresse IP source  <br/> |Adresse IP de destination  <br/> |Port source  <br/> |Port de destination  <br/> |Protocole  <br/> |Objectif  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Sortant  <br/> |IPs hôte Cloud Connector  <br/> |indifférent  <br/> |indifférent  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|Sortant  <br/> |IPs hôte Cloud Connector  <br/> |indifférent  <br/> |indifférent  <br/> |80, 443  <br/> |TCP  <br/> |Liste de révocation de certificats (CRL)  <br/> |
|Sortant  <br/> |IPs hôte Cloud Connector  <br/> |indifférent  <br/> |indifférent  <br/> |80, 443  <br/> |TCP  <br/> |Mise à jour de Cloud Connector  <br/> Skype Entreprise Online  <br/> PowerShell d’administration  <br/> Windows Update  <br/> |

Si des règles plus restrictives sont requises, reportez-vous aux URL de liste d’adresses autorisées suivantes :

- [URL de la liste de révocation de certificats](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) dans [les URL et plages d’adresses IP Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)

- Windows Update : [procédure de configuration d’un pare-feu pour les mises à jour logicielles](https://technet.microsoft.com/library/bb693717.aspx)

- Skype entreprise Online PowerShell admin : \*. online.Lync.com

    Si vous avez besoin d’une exclusion de proxy pour cette destination, vous devrez l’ajouter à la liste de contournement WinHTTP.

- Mise à jour de Cloud Connector : [https://go.microsoft.com](https://go.microsoft.com)Centre de [Téléchargement](https://aka.ms/CloudConnectorInstaller), et[https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>Résolution de noms DNS pour le composant Edge
<a name="BKMB_Ports"> </a>

Le composant Edge doit résoudre les noms externes des services Office 365 et les noms internes des autres composants de Cloud Connector.

Chaque composant Edge est un ordinateur multi-hébergé avec des interfaces internes et externes. Cloud Connector déploie des serveurs DNS sur le composant de contrôleur de domaine dans le réseau de périmètre. Vous pouvez pointer le serveur Edge vers le serveur DNS dans le périmètre pour toutes les résolutions de noms, mais vous devez activer le serveur DNS Cloud Connector pour résoudre les noms externes en définissant une zone DNS contenant un ou plusieurs enregistrements A DNS pour les requêtes externes qui font référence au nom recherches sur d’autres serveurs DNS publics.

Dans le fichier. ini, si vous définissez le nom de domaine complet pour les passerelles à partir du même espace de domaine que votre domaine SIP, la zone faisant autorité pour ce domaine SIP sera créée sur le serveur DNS dans le périmètre. Si le serveur Edge pointe vers ce serveur DNS pour résoudre les noms, Edge ne résoudra jamais le _sipfederationtls. \<enregistrement\> DNS votre_domaine, qui est requis pour le flux d’appels. Dans ce cas, Microsoft vous recommande de fournir un serveur DNS sur l’interface externe de serveur Edge pour résoudre les recherches de noms Internet, et chaque composant Edge doit utiliser un fichier hôte pour résoudre les autres noms de composants Cloud Connector en adresses IP.

> [!NOTE]
> Pour des raisons de sécurité, nous vous recommandons de ne pas faire pointer le serveur DNS Cloud Connector vers les serveurs internes dans le domaine de production pour la résolution de noms.

### <a name="determine-deployment-parameters"></a>Déterminer les paramètres de déploiement
<a name="BKMK_SiteParams"> </a>

Tout d’abord, vous devez définir les paramètres de déploiement courants suivants :


|**Élément**|**Description**|**Remarques**|
|:-----|:-----|:-----|
|Domaines SIP  <br/> |URI SIP utilisée par les utilisateurs de l’entreprise. Fournir tous les domaines SIP qui seront pris en charge par ce déploiement. Vous pouvez avoir plusieurs domaines SIP.  <br/> ||
|Nombre de sites RTC  <br/> |Nombre de sites RTC que vous allez déployer.  <br/> ||

Pour chaque site RTC que vous envisagez de déployer, vous devrez rassembler les informations suivantes avant de commencer le déploiement. Vous devrez fournir ces informations lors de la mise à jour du fichier CloudConnector. ini.

Lors de la configuration des informations de passerelle, rappelez-vous des points suivants :

- Si vous n’avez qu’une seule passerelle, supprimez la section dans le fichier. ini de la deuxième passerelle. S’il y a plus de deux passerelles, suivez le format existant pour en ajouter de nouvelles.

- Assurez-vous que l’adresse IP et le port de la (des) passerelle (s) sont corrects.

- Pour prendre en charge la haute disponibilité de niveau passerelle PSTN, conservez la passerelle secondaire ou ajoutez des passerelles supplémentaires.

Module Pour limiter les numéros d’appels sortants, mettez à jour la valeur LocalRoute.



|**Paramètres de site**|**Description**|**Remarques**|
|:-----|:-----|:-----|
|Nom de domaine de l’ordinateur virtuel  <br/> |Nom de domaine pour les composants internes de Cloud Connector. Ce domaine doit être différent du domaine de production. Le nom doit être le même pour toutes les appliances Cloud Connector.  <br/> Nom dans le fichier. ini : « VirtualMachineDomain »  <br/> |le domaine. local est préféré.  <br/> |
|Nom du contrôleur de domaine Cloud Connector  <br/> |Nom du contrôleur de domaine.  <br/> Nom dans le fichier. ini : « ServerName »  <br/> |Cette valeur doit être inférieure ou égale à 15 caractères. Entrez le nom NetBIOS uniquement.  <br/> |
|IP/masque de sous-réseau du contrôleur de domaine Cloud Connector  <br/> |Adresse IP du contrôleur de domaine.  <br/> Nom dans le fichier. ini : « IP »  <br/> ||
|Noms de domaine complets du service O365 Online  <br/> |Doit être la valeur par défaut dans la plupart des cas pour l’instance O365 internationale.  <br/> Nom dans le fichier. ini : « OnlineSipFederationFqdn »  <br/> ||
|SiteName  <br/> |Nom du site Skype entreprise ; par exemple, Seattle.  <br/> Nom dans le fichier. ini : « SiteName »  <br/> Pour la version 1.4.1 et les versions ultérieures, le nom du site doit être différent pour chaque site et le nom doit correspondre au site PSTN, s’il existe, défini dans Office 365. Notez que les sites RTC seront automatiquement créés lors de l’inscription de la première Appliance dans un site.  <br/> ||
|HardwareType  <br/> Version 1.4.1 et versions ultérieures  <br/> |Type de matériel. La valeur par défaut est Normal. Vous pouvez également définir sur minimum.  <br/> ||
|Country Code  <br/> |Indicatif du pays pour la numérotation.  <br/> Nom dans le fichier. ini : « CountryCode »  <br/> ||
|Ville  <br/> |Ville (facultatif).  <br/> Nom dans le fichier. ini : « City »  <br/> ||
|État  <br/> |État (facultatif).  <br/> Nom dans le fichier. ini : « état »  <br/> ||
|Adresse IP de l’ordinateur virtuel de base  <br/> |Adresse IP de la machine virtuelle de base temporaire qui sera utilisée pour créer le VHDX pour toutes les machines virtuelles de Cloud Connector. Cette adresse IP doit se trouver dans le même sous-réseau de réseau d’entreprise de périmètre défini à l’étape suivante et nécessite un accès à Internet. Veillez à définir la passerelle par défaut de l’entreprise et le DNS routable vers Internet.  <br/> Nom dans le fichier. ini : « BaseVMIP »  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> Version 1.4.1 et versions ultérieures  <br/> |L’adresse de Windows Server Update Services (WSUS), un serveur intranet qui héberge les mises à jour à partir de Microsoft Update.  <br/> Vous pouvez laisser le champ vide si WSUS n’est pas nécessaire.  <br/> ||
|Masque de sous-réseau pour le réseau interne  <br/> |Cloud Connector configure un réseau IP pour les communications internes entre les composants de Cloud Connector. Edge doit également être connecté à un autre sous-réseau qui permet la connexion à Internet.  <br/> Nom dans le fichier. ini : « CorpnetIPPrefixLength » sous « parameters for a pool of VM Network »  <br/> ||
|Masque de sous-réseau pour réseau externe  <br/> |Pour le réseau externe du composant Edge.  <br/> Nom dans le fichier. ini : « InternetIPPrefix » sous « parameters for a pool of VM Network »  <br/> ||
|Nom du commutateur pour le réseau interne  <br/> |Nom du commutateur qui sera utilisé pour le réseau interne de Cloud Connector.  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nom dans le fichier. ini : « CorpnetSwitchName » sous « parameters for a pool of VM Network »  <br/> ||
|Nom du commutateur pour le réseau externe  <br/> |Nom du commutateur qui sera utilisé pour le réseau de Cloud Connector externe.  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nom dans le fichier. ini : « InternetSwitchName » sous « parameters for a pool of VM Network »  <br/> ||
|Passerelle par défaut pour le réseau interne  <br/> |Cette passerelle doit fournir l’accès à Internet (Internet nécessite également la définition du serveur DNS) et sera configurée sur les interfaces internes des composants de Cloud Connector.  <br/> Nom dans le fichier. ini : « CorpnetDefaultGateway » sous « parameters for a pool of VM Network »  <br/> ||
|Passerelle par défaut pour l’interface externe du composant Edge  <br/> |Sera configuré sur l’interface externe du composant Edge.  <br/> Nom dans le fichier. ini : « InternetDefaultGateway » sous « parameters for a pool of VM Network »  <br/> ||
|Serveur DNS pour le réseau interne  <br/> |Sera configuré sur l’interface interne de la machine virtuelle temporaire. Doit fournir la résolution de noms pour les noms Internet. Si aucun serveur DNS n’est fourni, la connexion à Internet échouera et le déploiement ne s’achèvera pas.  <br/> Nom dans le fichier. ini : « CorpnetDNSIPAddress » sous « parameters for a pool of VM Network »  <br/> ||
|Serveur DNS pour l’interface externe du composant Edge  <br/> |Sera configuré sur l’interface externe du serveur Edge.  <br/> Nom dans le fichier. ini : « InternetDNSIPAddress » sous « parameters for a pool of VM Network »  <br/> ||
|Nom du commutateur de gestion  <br/> |Le commutateur de gestion est un commutateur temporaire qui sera créé automatiquement et utilisé pour la configuration de Cloud Connector pendant le déploiement. Elle sera déconnectée automatiquement après le déploiement. Il doit s’agir d’un sous-réseau différent de tous les autres réseaux utilisés dans Cloud Connector.  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nom dans le fichier. ini : « ManagementSwitchName » sous « parameters for a pool of VM Network »  <br/> ||
|Adresse de sous-réseau de gestion/masque de sous-réseau  <br/> |Le sous-réseau de gestion est un sous-réseau temporaire qui sera créé automatiquement et qui sera utilisé pour la configuration de Cloud Connector pendant le déploiement. Elle sera supprimée automatiquement après le déploiement. Il doit s’agir d’un sous-réseau différent de tous les autres réseaux utilisés dans Cloud Connector.  <br/> Noms dans le fichier. ini : « ManagementIPPrefix » et « ManagementIPPrefixLength » sous « parameters for a pool of VM Network »  <br/> ||
|Ordinateur du magasin central de gestion (CMS)  <br/> |Nom de domaine complet unique utilisé pour le magasin central de gestion (CMS). Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nom dans le fichier. ini : « ServerName » sous « parameters for Primary Central Management Service »  <br/> |Cette valeur doit être inférieure ou égale à 15 caractères. Entrez le nom NetBIOS uniquement.  <br/> (Nom du pool CMS = nom du serveur)  <br/> |
|Adresse IP de l’ordinateur CMS  <br/> |Adresse IP du serveur CMS (interne dans le réseau de périmètre).  <br/> Nom dans le fichier INI : « IP » sous « parameters for Primary Central Management Service »  <br/> ||
|Nom de partage de fichiers  <br/> |Nom de partage de fichiers à créer sur le serveur CMS pour les données de réplication Skype entreprise (par exemple, CmsFileStore).  <br/> Dans la plupart des cas, la valeur suggérée par défaut peut être utilisée.  <br/> Nom dans le fichier. ini : « CmsFileStore » sous « parameters for Primary Central Management Service »  <br/> ||
|Nom du pool du composant de médiation  <br/> |Nom du pool du composant de médiation. Entrez le nom NetBIOS uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nom dans le fichier. ini : « PoolName » sous « parameters for a pool of Mediation Servers »  <br/> |Cette valeur doit être inférieure ou égale à 15 caractères. Entrez le nom NetBIOS uniquement.  <br/> |
|Nom du composant de médiation  <br/> |Nom du composant de médiation 1. Entrez le nom NetBIOS uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nom dans le fichier. ini : « ServerName » sous « parameters for a pool of Mediation Servers »  <br/> |Cette valeur doit être inférieure ou égale à 15 caractères. Entrez le nom NetBIOS uniquement.  <br/> |
|Adresse IP de l’ordinateur du composant de médiation  <br/> |Adresse IP du réseau d’entreprise interne pour le composant de médiation (interne au réseau de périmètre).  <br/> Nom dans le fichier. ini : « IP » sous « parameters for a pool of Mediation Servers »  <br/> ||
|Nom interne du pool de serveurs de périphérie  <br/> |Nom du pool du composant Edge. Entrez le nom NetBIOS uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nom dans le fichier. ini : « InternalPoolName » sous « parameters for a pool of Edge Servers »  <br/> |Cette valeur doit être inférieure ou égale à 15 caractères. Entrez le nom NetBIOS uniquement.  <br/> |
|Nom interne du serveur Edge  <br/> |Nom du composant du serveur Edge. Entrez le nom NetBIOS uniquement. Le nom de domaine AD sera utilisé pour générer le nom de domaine complet.  <br/> Nom dans le fichier. ini : « InternalServerName » sous « parameters for a pool of Edge Servers »  <br/> |Cette valeur doit être inférieure ou égale à 15 caractères. Entrez le nom NetBIOS uniquement.  <br/> |
|Adresse IP interne du serveur Edge  <br/> |Adresse IP du réseau de périmètre interne du composant Edge permettant de communiquer avec les autres composants de Cloud Connector.  <br/> Nom dans le fichier. ini : « InternalServerIPs » sous « parameters for a pool of Edge Servers »  <br/> ||
|Nom externe du pool d’accès  <br/> |Nom du serveur Edge d’accès ; par exemple, AP. Ce nom doit correspondre au nom fourni pour le certificat SSL. Entrez le nom NetBIOS uniquement. Le nom de domaine SIP sera utilisé pour générer le nom de domaine complet (FQDN). Un nom de pool externe sera utilisé pour tous les composants Edge du pool. Un seul pool d’accès Edge est requis par site RTC.  <br/> Nom dans le fichier. ini : « ExternalSIPPoolName » sous « parameters for a pool of Edge Servers »  <br/> |Cette valeur doit être inférieure ou égale à 15 caractères. Entrez le nom NetBIOS uniquement.  <br/> « SIP » est réservé et ne peut donc pas être utilisé comme nom.  <br/> Le nom de domaine complet généré doit correspondre au nom fourni pour le certificat SSL.  <br/> |
|Adresse IP externe du serveur Edge d’accès  <br/> |IP externe du composant Edge : adresse IP publique si aucune interface NAT n’est disponible ou adresse IP traduite (spécifiez les deux adresses si elles sont mappées).  <br/> Nom dans le fichier. ini : « Externalsipip » sous « parameters for a pool of Edge Servers »  <br/> ||
|Nom du relais multimédia  <br/> |Nom du serveur Edge vidéo relais audio ; par exemple, m. Un nom de pool externe sera utilisé pour tous les composants Edge d’un pool. Un pool de serveur relais multimédia Edge est requis par site RTC.  <br/> Nom dans le fichier. ini : « ExternalMRFQDNPoolName » sous « parameters for a pool of Edge Servers »  <br/> |Cette valeur doit être inférieure ou égale à 15 caractères. Entrez le nom NetBIOS uniquement.  <br/> |
|IP externe du serveur Edge du serveur relais multimédia  <br/> |Actuellement, une seule adresse IP est prise en charge, de sorte qu’il s’agit de la même adresse IP que le serveur Edge d’accès, public ou IP mappé (spécifiez les deux adresses si elles sont mappées). Il peut s’agir de l’adresse IP externe du serveur Edge d’accès. Remarque Si le serveur Edge est derrière NAT, vous devez également spécifier la valeur du paramètre Next.  <br/> Nom dans le fichier. ini : « Externalmrip » sous « parameters for a pool of Edge Servers »  <br/> ||
|Adresse IP externe du serveur Edge relais multimédia (si le serveur Edge est derrière NAT)  <br/> |Si votre serveur Edge est derrière NAT, vous devez également spécifier l’adresse publique du périphérique NAT.  <br/> Nom dans le fichier. ini : « ExternalMRPublicIPs » sous « parameters for a pool of Edge Servers »  <br/> ||
|Marque et modèle de la passerelle vocale 1  <br/> |Spécifiez la marque et le modèle de la passerelle SBC/voix. Notez que vous pouvez connecter un périphérique ou une jonction SIP à partir de la liste des [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP)appareils testés à l’adresse.  <br/> ||
|Marque et modèle de la passerelle vocale 2 (copiez cette ligne si votre installation comporte plus de 2 passerelles)  <br/> |Spécifiez la marque et le modèle de la passerelle vocale. Notez que vous pouvez connecter un périphérique à partir de la liste des appareils [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP)testés à l’adresse.  <br/> ||
|Nom de la passerelle vocale 1  <br/> |Permet de générer le nom de domaine complet de l’ordinateur avec le domaine AD. Obligatoire si TLS est utilisé entre le composant de médiation et la passerelle vocale. Si vous ne prévoyez pas d’utiliser le nom de domaine complet (par exemple, TLS n’est pas requis) ou si la passerelle vocale ne prend pas en charge la connexion à l’aide du nom de domaine complet (IP uniquement), indiquez.  <br/> ||
|Nom de la passerelle vocale 2 (copiez cette ligne si votre installation comporte plus de 2 passerelles)  <br/> |Permet de générer le nom de domaine complet de l’ordinateur avec le domaine AD. Obligatoire si TLS est utilisé entre le composant de médiation et la passerelle vocale. Si vous ne prévoyez pas d’utiliser le nom de domaine complet (par exemple, TLS n’est pas requis) ou si la passerelle vocale ne prend pas en charge la connexion à l’aide du nom de domaine complet (IP uniquement), indiquez.  <br/> ||
|Adresse IP de la passerelle vocale 1  <br/> |Adresse IP de la passerelle vocale.  <br/> ||
|Adresse IP de la passerelle vocale 2 (copiez cette ligne si votre installation comporte plus de 2 passerelles)  <br/> |Adresse IP de la passerelle vocale.  <br/> ||
|Numéro de port de la passerelle vocale 1 (copiez cette ligne si votre installation comporte plus de 2 passerelles)  <br/> |Port d’écoute de la jonction SIP de la passerelle vocale, par exemple 5060.  <br/> ||
|Port de la passerelle vocale 2 #  <br/> |Port d’écoute de la jonction SIP de la passerelle vocale, par exemple 5060.  <br/> ||
|Protocole de la passerelle vocale 1 pour le trafic SIP  <br/> |TCP ou TLS.  <br/> ||
|Protocole de la passerelle vocale 2 pour le trafic SIP (copiez cette ligne si votre installation comporte plus de 2 passerelles)  <br/> |TCP ou TLS.  <br/> ||
|Plage de ports multimédias externes pour le trafic vers et depuis le composant Edge  <br/> |Plage de ports TCP/UDP pour le trafic multimédia vers et depuis l’interface externe du serveur Edge. Doit toujours commencer à partir de 50 000. Pour plus d’informations, reportez-vous à la rubrique « ports et protocoles ».  <br/> |50000-59 999  <br/> |
|Plage de ports multimédias permettant de communiquer avec le composant de médiation via le pare-feu interne  <br/> |Plage de ports UDP que le composant de médiation utilisera pour communiquer avec les clients et les passerelles (Recommendation 4 ports per Call).  <br/> ||
|Plage de ports multimédias permettant de communiquer avec le client Skype entreprise via un pare-feu interne  <br/> |À des fins de planification, ne peut pas être modifié. Les ports doivent être ouverts dans le pare-feu interne pour pouvoir communiquer entre les clients Skype entreprise à l’intérieur du réseau interne et avec le composant de médiation.  <br/> |50 000-50 019  <br/> |
|Mot de passe du certificat public  <br/> |Doit être fourni dans le script.  <br/> ||
|Mot de passe administrateur en mode sans échec  <br/> Version 1.4.2 uniquement  <br/> |Mot de passe administrateur en mode sans échec pour le domaine interne de CC.  <br/> ||
|Mot de passe de l’administrateur de domaine Cloud Connector  <br/> Version 1.4.2 uniquement  <br/> |Mot de passe de l’administrateur de domaine Cloud Connector (différent de votre domaine de production). Le nom d’utilisateur est administrateur. Vous ne pouvez pas modifier le nom de l’utilisateur.  <br/> ||
|Mot de passe administrateur des ordinateurs virtuels  <br/> Version 1.4.2 uniquement  <br/> |Permet de configurer le réseau de gestion pendant le déploiement.  <br/> Le nom d’utilisateur est administrateur. Vous ne pouvez pas modifier le nom de l’utilisateur.  <br/> ||
|CABackupFile  <br/> Version 2,0 et versions ultérieures  <br/> |Permet d’enregistrer le service d’autorité de certification à partir du serveur Active Directory vers un fichier lors du déploiement de plusieurs Appliances dans un site Cloud Connector. Veillez à utiliser le même mot de passe pour toutes les appliances sur un même site Cloud Connector afin d’importer le fichier de sauvegarde de l’autorité de certification vers le nouvel équipement ajouté.  <br/> ||
|CCEService  <br/> Version 2,0 et versions ultérieures  <br/> |Utilisé pour le service de gestion de Cloud Connector ; doit accéder à l’annuaire de sites Cloud Connector. Veillez à utiliser le même mot de passe pour toutes les appliances sur un même site Cloud Connector.  <br/> ||
|Administrateur client Office 365  <br/> | Le compte est utilisé par Cloud Connector pour mettre à jour et gérer les paramètres de client pour Cloud Connector : <br/>  Version 2,0 et versions ultérieures : informations d’identification pour un compte Office 365 dédié avec des droits d’administrateur de Skype entreprise. <br/>  Versions antérieures à 2,0 : informations d’identification pour un compte Office 365 dédié avec des droits d’administrateur client globaux. <br/> ||
|Activer la prise en charge de REFER  <br/> |Cela déterminera si la prise en charge de SIP REFER est activée ou désactivée sur la configuration de jonction vers votre IP/PBX. La valeur par défaut est True. Si votre passerelle IP/PBX prend en charge le support technique, conservez la valeur true. Si ce n’est pas le cas, cette valeur doit être remplacée par false. Si vous n’êtes pas certain que votre passerelle prend en charge REFER, veuillez consulter la rubrique [IP-PBX et passerelles qualifiés](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).   <br/> ||
|EnableFastFailoverTimer  <br/> Version 2,0 et versions ultérieures  <br/> |Avec la valeur par défaut « true », si la passerelle ne répond pas aux appels sortants dans un délai de 10 secondes, ils seront routés vers la passerelle disponible suivante ; s’il n’y a pas de jonctions supplémentaires, l’appel sera automatiquement abandonné.  <br/> Toutefois, dans une organisation dont les réseaux et les réponses de passerelle sont lents, ou lorsque le processus d’établissement des appels prend plus de 10 secondes, cela peut entraîner l’abandon inutile des appels.  <br/> Lorsque vous effectuez des appels vers certains pays, par exemple l’Émirats Arabes Unis ou l’Afghanistan, le processus de mise en place de l’appel peut prendre plus de 10 secondes. Vous devrez modifier la valeur sur false si vous rencontrez des problèmes similaires. N’oubliez pas de modifier le paramètre correspondant sur l’SBC ou la passerelle connecté.  <br/> La valeur peut être true ou false. La valeur par défaut est True.  <br/> ||
|ForwardCallHistory  <br/> Version 2,0 et versions ultérieures  <br/> | Ce paramètre est utilisé pour activer les en-têtes SIP utilisés pour signaler l’appelant initial dans les scénarios de sonnerie simultanée, de transfert d’appel et de transfert d’appel. Si le paramètre est défini sur true, deux en-têtes SIP sont activés : <br/>  Historique-informations <br/>  Référencé par <br/>  L’en-tête History-Info est utilisé pour recibler les demandes SIP et « fournir (s) » un mécanisme standard pour capturer les informations d’historique des requêtes afin d’activer un large éventail de services pour les réseaux et les utilisateurs finaux» ([RFC 4244-Section 1,1](http://www.ietf.org/rfc/rfc4244.txt)). Pour les interfaces de jonction Cloud Connector, cela est utilisé dans sonnerie simultanée et les scénarios de transfert d’appel.  <br/>  La valeur peut être true ou false. La valeur par défaut est False. <br/> ||
|Transférer PAI  <br/> Version 2,0 et versions ultérieures  <br/> |PAI est une extension privée de SIP qui permet aux serveurs SIP d’affirmer l’identité des utilisateurs authentifiés. Pour le fournisseur de jonctions SIP, PAI peut être utilisé à des fins de facturation dans le cas où les en-têtes History-Info et expertisé-by sont absents. Lorsque le transfert P-asserted-Identity est activé dans la configuration, le serveur de médiation transfère les en &amp; -têtes PAI avec des URI de type SIP de Cloud Connector vers la jonction SIP. Le serveur de médiation transfère les en-têtes PAI avec les &amp; numéros E. 164 de l’URI tel uniquement sur la jonction SIP vers Cloud Connector. Le serveur de médiation transfère également tous les en-têtes de confidentialité reçus dans les deux sens. Si la demande SIP envoyée par le serveur de médiation inclut un en-tête de confidentialité du formulaire-« Privacy : ID » en combinaison avec l’en-tête PAI, l’identité affirmée doit rester privée en dehors du domaine d’approbation réseau.  <br/> La valeur peut être true ou false. La valeur par défaut est False.  <br/> ||

### <a name="certificate-requirements"></a>Spécifications des certificats
<a name="BKMK_Certs"> </a>

Chaque composant Edge nécessite un certificat d’une autorité de certification publique. Les certificats doivent disposer d’une clé privée exportable pour pouvoir être copiés entre les composants Edge. Pour répondre aux exigences de certificat, vous devez choisir entre les options suivantes et fournir le nom de sujet (SN) et l’autre nom de sujet (SAN) pour le certificat.

 **Si vous disposez d’un domaine SIP unique :**

- **Option 1.** Le nom de sujet doit contenir le nom du pool que vous avez affecté aux composants Edge. Notez que le nom de l’objet ne peut pas être sip.sipdomain.com, car ce nom est réservé au composant Microsoft Edge Skype entreprise online. Le SAN doit contenir sip.sipdomain.com et le nom du pool Edge d’accès :

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **Option 2.** Si vous souhaitez utiliser un seul certificat générique sur tous les serveurs de pool Edge que vous déployez, vous pouvez utiliser une entrée SAN générique \*de. sipdomain.com au lieu du nom du pool de serveurs Edge dans le certificat. Le nom du sujet peut être le nom du pool de serveurs Edge d’accès de l’un des pools de serveurs Edge que vous avez déployés :

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> Vous ne devez pas créer une entrée DNS externe pour SIP. \<sipdomain\>. com, car ce nom appartient au déploiement d’Office 365.

> [!NOTE]
> Si vous souhaitez utiliser un certificat unique pour tous les pools de serveurs Edge déployés dans votre organisation et que vous ne pouvez pas utiliser un certificat de caractère générique tel que défini dans l’option 2, vous devez inclure le nom de domaine complet (FQDN) pour tous les pools de serveurs Edge déployés dans le nom de SAN du certificat.

 **Si vous avez plusieurs domaines SIP :**

Vous devrez ajouter sip.sipdomain.com pour chaque domaine SIP et le nom des pools de serveurs Edge d’accès par domaine (il peut s’agir d’un pool physique, mais avec des noms différents). Voici un exemple d’entrées SN et SAN dans un scénario de domaine SIP multiple :

- **Option 1.** Le nom de sujet doit contenir le nom du pool que vous avez affecté aux composants Edge. Notez que le nom de l’objet ne peut pas être sip.sipdomain.com, car ce nom est réservé au composant Microsoft Edge Skype entreprise online. Le SAN doit contenir sip.sipdomain.com et le nom du pool Edge d’accès :

  ```console
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>Option 2.</strong> Si vous souhaitez utiliser un seul certificat générique sur tous les serveurs de pool Edge que vous déployez, vous pouvez utiliser une entrée SAN générique \*de. sipdomain.com au lieu du nom du pool de serveurs Edge dans le certificat. Le nom du sujet peut être le nom du pool de serveurs Edge d’accès de l’un des pools de serveurs Edge que vous avez déployés :

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> Vous ne devez pas créer une entrée DNS externe pour SIP. \<sipdomain\>. com, car ce nom appartient au déploiement d’Office 365.

À des fins de déploiement, vous pouvez utiliser le tableau suivant :

|**Option**|**Description**|**Remarques**|
|:-----|:-----|:-----|
|Quelle option allez-vous utiliser pour votre déploiement ?  <br/> |Option 1 ou 2  <br/> ||
|SN  <br/> |Fournir le SN de votre certificat  <br/> ||
|SAN  <br/> |Fournit le SAN pour votre certificat  <br/> ||

Si vous utilisez TLS entre la passerelle et le serveur de médiation, vous devrez obtenir le certificat racine, ou la chaîne de certificats complète, pour le certificat affecté à la passerelle.

## <a name="dial-plan-considerations"></a>Considérations relatives au plan de numérotation
<a name="BKMK_DailPlan"> </a>

Cloud Connector nécessite l’utilisation d’un plan de numérotation en ligne. Pour plus d’informations sur la configuration d’un plan de numérotation en ligne, voir [qu’est-ce que les plans de numérotation ?](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>Considérations relatives à la haute disponibilité
<a name="BKMK_HA"> </a>

Lorsque vous déployez Cloud Connector Edition pour une haute disponibilité, vous déployez au moins deux Appliances qui font office de sauvegarde. Chaque appliance se compose de quatre composants : Edge, médiation, magasin central de gestion (CMS) et contrôleur de domaine.

En général, si un composant au sein d’une appliance tombe en panne, la version Cloud Connector Edition peut continuer à gérer les appels, mais vous devez prendre en compte les éléments suivants :

- **Considérations sur les composants de médiation, CMS et de contrôleur de domaine**

    Supposons que le MCG ou le composant contrôleur de domaine d’une appliance tombe en panne. L’appliance peut toujours traiter les appels entrants et sortants, mais si vous redémarrez un composant de médiation alors que le contrôleur de domaine ou le composant CMS n’est pas accessible, la médiation ne fonctionnera pas. Il en va de même pour le redémarrage du composant CMS lorsque le contrôleur de domaine est inactif.

    **Recommandation :** Avant de relancer les composants, vérifiez la disponibilité des autres composants dans l’appliance.

- **Considérations relatives aux composants de serveur Edge**

    Si le composant Edge d’une appliance n’est pas disponible, le comportement pour les appels entrants et sortants diffère comme suit :

  - **Appel sortant**: appel de votre utilisateur sur Internet à un réseau PSTN.

    Le mécanisme de distribution d’appels dans le Cloud identifiera le fait que l’un des composants Edge est hors service et acheminera tous les appels vers une autre appliance, afin que l’appel sortant aboutisse.

  - **Appel entrant**— un appel depuis le réseau RTC vers un utilisateur qui se trouve sur un réseau local ou sur Internet.

     Si le composant Edge de l’appliance qui a reçu l’appel ne fonctionne pas, les appels entrants vers cette appliance échouent car le composant de médiation ne peut pas rediriger l’appel vers le composant Edge de l’autre appliance.

    **Recommandation :** Disposer d’un système de surveillance. Après avoir identifié un dysfonctionnement du composant Edge, arrêtez tous les composants de l’appliance sur lesquels le composant Edge n’est pas disponible.

## <a name="cloud-connector-media-flow"></a>Flux multimédia de Cloud Connector
<a name="BKMK_MediaFlow"> </a>

Les diagrammes suivants décrivent le flux d’un appel entrant et sortant via la version Cloud Connector. Il s’agit d’informations utiles pour comprendre comment la connectivité est établie.

Dans le premier diagramme, un utilisateur interne place un appel sortant comme suit :

1. Dave, un utilisateur hébergé en ligne, mais maintenant sur le réseau interne, appelle un utilisateur RTC externe.

2. Le trafic SIP est acheminé vers Skype entreprise online.

3. Skype entreprise Online effectue une recherche inversée de numéros du numéro. La recherche de numéro inverse échoue, car ce numéro n’appartient à personne de l’organisation Skype entreprise.

4. L’appel est acheminé vers le composant Edge (trafic SIP et multimédia par le biais du serveur Edge en ligne ; Le média est dirigé vers le composant de médiation via le pare-feu interne).

5. Si l’itinéraire existe, le composant Edge relaie le trafic vers le composant de médiation dans le réseau de périmètre.

6. Le composant de médiation envoie le trafic vers la passerelle PSTN.

![Flux de média sortant pour Cloud Connector](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

Dans le diagramme suivant, un utilisateur interne reçoit un appel entrant comme suit :

1. La passerelle PSTN reçoit un appel pour l’utilisateur Dave, qui est hébergé en ligne, mais qui se trouve maintenant sur le réseau interne.

2. Le trafic SIP est acheminé vers le composant de médiation.

3. Le composant de médiation envoie le trafic SIP vers le composant Edge, puis vers Skype entreprise online.

4. Skype entreprise Online effectue une recherche inversée de numéros et indique qu’il s’agit d’un utilisateur Dave.

5. La signalisation SIP est dirigée vers tous les points de présence de Dave.

6. Le trafic multimédia est établi entre la passerelle et le composant de médiation, ainsi qu’entre le composant de médiation et le point de terminaison.

![Flux de médias entrants pour Cloud Connector](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>Analyse et dépannage
<a name="BKMK_Monitor"> </a>

Le mécanisme de surveillance et de résolution des problèmes est installé automatiquement avec chaque appliance Cloud Connector. Le mécanisme détecte les événements suivants :

- Une ou plusieurs machines virtuelles d’une appliance Cloud Connector ne sont pas connectées à un commutateur virtuel Internet ou interne.

- Une ou plusieurs machines virtuelles d’une appliance Cloud Connector sont à l’état enregistré ou arrêté.

- Les services qui ne sont pas en cours d’exécution ;

  Si l’un des événements suivants est détecté, l’ensemble de l’appliance Cloud Connector est vidé et marqué comme étant hors connexion pour empêcher la tentative d’établir des appels à un appareil défectueux. Les fonctionnalités de récupération automatique de Cloud Connector vont restaurer les services et marquer l’appliance comme étant en ligne. Si la récupération automatique échoue pour une raison quelconque, reportez-vous à [la rubrique troubleshoot your Cloud Connector Deployment](troubleshoot-your-cloud-connector-deployment.md).

  - Sur la machine virtuelle du magasin central de gestion :

     - Agent réplicateur principal Skype entreprise

     - Agent réplicateur de réplicas Skype entreprise

  - Sur la machine virtuelle du serveur de médiation :

     - Agent réplicateur de réplicas Skype entreprise

     - Médiation de Skype entreprise Server

  - Sur la machine virtuelle du serveur Edge

     - Agent réplicateur de réplicas Skype entreprise

     -  Serveur Edge d’accès Skype entreprise

     - Serveur Edge audio/vidéo Skype entreprise Server

     - Authentification audio/vidéo Skype entreprise Server

     - Serveur Edge de conférence Web Skype entreprise Server

- Règle de trafic entrant du pare-feu Windows pour « CS RTCSRV » sur Edge, « CS RTCMEDSRV » sur le serveur de médiation est désactivé.

Cloud Connector 2,1 et versions ultérieures prend en charge la surveillance de Cloud Connector à l’aide d’Operations Management Suite (OMS). Pour plus d’informations, consultez la rubrique [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md) .

## <a name="for-more-information"></a>Pour plus d'informations
<a name="BKMK_MoreInfo"> </a>

Pour plus d’informations, voir les commandes suivantes :

- [Solutions de téléphonie Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)

- [Configuration et gestion de Skype entreprise, version Cloud Connector](configure-skype-for-business-cloud-connector-edition.md)

- [Planification de la déviation du trafic multimédia dans Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

- [Déploiement de la déviation du trafic multimédia dans Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)


