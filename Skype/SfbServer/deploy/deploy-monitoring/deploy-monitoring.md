---
title: Déployer la surveillance dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 'Résumé : Découvrez comment déployer la surveillance dans Skype Entreprise Server.'
ms.openlocfilehash: 5e3fdf468067b707ee1dd97c5458f3612d78653d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855078"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>Déployer la surveillance dans Skype Entreprise Server

**Résumé :** Découvrez comment déployer la surveillance dans Skype Entreprise Server.

Avant d’effectuer ces tâches, [examinez planifier la surveillance dans Skype Entreprise Server](../../plan-your-deployment/monitoring.md).

En règle générale, vous implémentez des services de surveillance au sein de votre topologie en effectuant les deux étapes suivantes :

1. Activation de la surveillance en même temps que la mise en place d’Skype Entreprise Server pool. (Dans Skype Entreprise Server, la surveillance est activée ou désactivée pool par pool.) Notez que vous pouvez activer la surveillance pour un pool sans réellement collecter de données de surveillance, un processus expliqué dans la section Configuration de l’enregistrement des détails des appels et de la qualité de l’expérience Paramètres de cette documentation.

2. Association d’un magasin d’analyse (c’est-à-dire une base de données de surveillance) au nouveau pool. Notez qu’un seul magasin d’analyse peut être associé à plusieurs pools. Selon le nombre d’utilisateurs hébergés sur vos pools de serveurs d’inscriptions, cela signifie que vous n’avez pas besoin de configurer une base de données de surveillance distincte pour chacun de vos pools. Un seul magasin d’analyse peut être utilisé par plusieurs pools.

Bien qu’il soit souvent plus simple d’activer la surveillance en même temps que vous créez un nouveau pool, il est également possible de créer un nouveau pool en désactivant la surveillance. Dans ce cas, vous pouvez ultérieurement utiliser le Générateur de topologie pour activer le service : le Générateur de topologie permet d’activer ou de désactiver la surveillance pour un pool ou d’associer un pool à un magasin d’analyse différent. N’oubliez pas que même s’il n’existe plus de rôle serveur de surveillance, vous devrez créer un ou plusieurs magasins de surveillance : des bases de données principale utilisées pour stocker les données recueillies par le service de surveillance. Ces bases de données principale peuvent être créées à l’aide de Microsoft SQL Server 2008 R2, Microsoft SQL Server 2012, Microsoft SQL Server 2014 ou Microsoft SQL Server 2019.

> [!NOTE]
> Si la surveillance a été activée pour un pool, vous pouvez désactiver le processus de collecte des données de surveillance sans avoir à modifier votre topologie : Skype Entreprise Server vous permet de désactiver (puis de réactiver) la collecte de données d’enregistrement des détails des appels (CDR) ou de qualité de l’expérience (QoE). Pour plus d’informations, voir la section Configuration de l’enregistrement des détails des appels et de la qualité de l’expérience de ce document.

Une autre amélioration importante de la surveillance dans Skype Entreprise Server est le fait que les rapports de surveillance Skype Entreprise Server désormais prendre en charge IPv6 : les rapports qui utilisent le champ Adresse IP affichent les adresses IPv4 ou IPv6 en fonction de : 1) la requête SQL utilisée ; et, 2) où l’adresse IPv6 est stockée ou non dans la base de données de surveillance.

> [!NOTE]
> Assurez-vous que le type de démarrage du service d’agent SQL Server est automatique et que le service d’agent SQL Server est en cours d’exécution pour l’instance SQL qui contient les bases de données de surveillance, afin que les travaux de maintenance de l’SQL Server de surveillance par défaut peuvent s’exécuter sur leur base programmée sous le contrôle du service d’agent SQL Server.

Cette documentation vous indique le processus d’installation et de configuration des rapports de surveillance et de surveillance pour Skype Entreprise Server. La documentation donne des instructions détaillées qui vous aideront à effectuer les opérations suivantes :

- activer la surveillance dans votre topologie et associer un magasin d’analyse à un pool frontal ;

- Installez SQL Server Reporting Services et les rapports Skype Entreprise Server surveillance. Les rapports de surveillance sont des rapports préconfigurés qui permettent de visualiser différemment les informations stockées dans une base de données de surveillance ;

- Configurez la collecte de données d’enregistrement des détails des appels (CDR) et de qualité de l’expérience (QoE). L’enregistrement des détails des appels vous permet de suivre l’utilisation de fonctionnalités Skype Entreprise Server telles que les appels téléphoniques VoIP (Voice over IP). messagerie instantanée ; transferts de fichiers ; conférence audio/vidéo (A/V) ; et sessions de partage d’application. Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et la « gigue » (différences de retard des paquets) ;

- vider manuellement les enregistrements des détails des appels et/ou QoE de la base de données de surveillance.

## <a name="deployment-checklist-for-monitoring"></a>Liste de vérification du déploiement pour la surveillance

Bien que la surveillance soit déjà installée et activée sur chaque serveur frontal, vous devez effectuer plusieurs étapes avant de pouvoir réellement collecter des données de surveillance pour Skype Entreprise Server. Ces étapes sont décrites dans la liste de vérification suivante :

|**Étape**|**Étapes**|**Appartenance aux rôles et groupes**|**Documentation**|
|:-----|:-----|:-----|:-----|
|**Installer le matériel et les logiciels prérequis** <br/> |Installez une version prise en charge de Microsoft SQL Server sur l’ordinateur qui fera office de magasin de données principal pour la surveillance.  <br/> |Utilisateur de domaine qui est également membre du groupe Administrateurs local.  <br/> |[Matériel pris en charge](/previous-versions/office/lync-server-2013/lync-server-2013-supported-hardware) <br/> [Prise en charge des logiciels des serveurs et de l’infrastructure](/previous-versions/office/lync-server-2013/lync-server-2013-server-software-and-infrastructure-support) <br/> |
|**Créer la topologie interne appropriée pour prendre en charge la surveillance** <br/> |Utilisez Skype Entreprise Server générateur de topologie pour ajouter des bases de données de surveillance à la topologie, puis publiez la topologie mise à jour.  <br/> |Pour définir une topologie, utilisateur membre du groupe Utilisateurs local.  <br/> Pour publier la topologie, utilisateur membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.  <br/> |[Associer un magasin d’analyse à un pool frontal dans Skype Entreprise Server](associate-a-monitoring-store.md) <br/> |
|**Activer les paramètres de surveillance appropriés** <br/> |Activer la surveillance de l’enregistrement des détails des appels (CDR) et/ou de la qualité de l’expérience (QoE) au niveau des étendues globale et/ou site.  <br/> |Utilisateur membre du groupe RTCUniversalServerAdmins ou disposant d’un rôle RBAC qui permet d’accéder aux applets de commande CsCdrConfiguration et CsQoEConfiguration.  <br/> |[Configurer les paramètres d’enregistrement des détails des appels et de qualité de l’expérience dans Skype Entreprise Server](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>Activer la surveillance

Bien que les agents de collecte de données unifiés soient automatiquement installés et activés sur chaque serveur frontal, cela ne signifie pas que vous commencerez automatiquement à collecter des données de surveillance dès que vous aurez terminé l’installation Skype Entreprise Server. À la place, vous devez faire deux choses : vous devez associer vos serveurs frontux/pools frontux à une base de données de surveillance et activer la surveillance de l’enregistrement des détails des appels (CDR) et/ou de la qualité de l’expérience (QoE) au niveau de l’étendue globale et/ou de l’étendue Site.

Pour obtenir des instructions détaillées sur l’association de serveurs frontaux ou de pools frontaux à une base de données de surveillance, voir la rubrique Associer un magasin d’analyse à un pool frontal dans [Skype Entreprise Server](associate-a-monitoring-store.md) dans le guide de déploiement. Une fois ces associations réalisées et une fois votre nouvelle topologie Skype Entreprise Server publiée, vous ne pourrez toujours pas collecter de données de surveillance. En effet, par défaut, la collecte de données CDR et QoE est désactivée lorsque vous installez Skype Entreprise Server.

Afin de pouvoir commencer la collecte de données, vous devez activer la surveillance des enregistrements des détails des appels et/ou la surveillance des données de qualité de l’expérience. (Notez que vous n’avez pas besoin d’activer la surveillance CDR et QoE ; si vous préférez, vous pouvez activer un type de surveillance tout en laissant l’autre type désactivé.) Pour activer la surveillance des cdR au niveau de l’étendue globale, exécutez la commande suivante à partir de Skype Entreprise Server Management Shell :

```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Vous pouvez également activer la surveillance de l’cdr à partir du panneau de Skype Entreprise Server de contrôle. Dans le Panneau de Skype Entreprise Server, complétez la procédure suivante :

1. Cliquez sur **Surveillance**.

2. Sous l’onglet **Enregistrement des détails des appels**, double-cliquez sur le paramètre **Global**.

3. Dans le volet **Paramètre de l’enregistrement des détails des appels (CDR)**, sélectionnez **Activer la surveillance des enregistrements des détails des appels**, puis cliquez sur **Valider**.

Pour activer la surveillance QoE au niveau de l’étendue globale, exécutez la commande Skype Entreprise Server Management Shell :

```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

Si vous préférez, vous pouvez également activer la surveillance QoE à partir du Panneau de Skype Entreprise Server de contrôle. Dans le Panneau de configuration, effectuez la procédure suivante :

1. Cliquez sur **Surveillance**.

2. Sous l’onglet **Données de qualité de l’expérience**, double-cliquez sur le paramètre **Global**.

3. Dans le volet **Paramètre de qualité de l’expérience (QoE)**, sélectionnez **Activer la surveillance des données de qualité de l’expérience**, puis cliquez sur **Valider**.

Comme indiqué, les exemples précédents activent la surveillance au niveau de l’étendue globale ; ils activent les surveillances CDR et QoE dans toute votre organisation. Vous pouvez également créer des paramètres de configuration CDR et QoE distincts au niveau de l’étendue du site, puis activer ou désactiver de façon sélective la surveillance pour chaque site. Par exemple, vous pouvez activer la surveillance CDR pour votre site de Redmond et la désactiver pour votre site de Dublin. Pour plus d’informations sur la gestion de vos paramètres de configuration d’analyse, voir la rubrique du guide de déploiement Configurer l’enregistrement des détails des appels et les paramètres de qualité de [l’expérience dans Skype Entreprise Server](call-detail-recording-and-qoe.md).

## <a name="see-also"></a>Voir aussi

[Planifier la surveillance dans Skype Entreprise Server](../../plan-your-deployment/monitoring.md)