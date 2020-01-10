---
title: Déploiement de la surveillance dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 'Résumé : Découvrez comment déployer le contrôle dans Skype entreprise Server.'
ms.openlocfilehash: 7f3bd96b814b45b625612aae9b56a706dfff470f
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001145"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>Déploiement de la surveillance dans Skype entreprise Server

**Résumé :** Découvrez comment déployer le contrôle dans Skype entreprise Server.

Avant d’effectuer ces tâches, reportez-vous [à la planification de l’analyse dans Skype entreprise Server](../../plan-your-deployment/monitoring.md).

Vous implémenterez généralement les services de surveillance au sein de votre topologie en effectuant les deux étapes suivantes :

1. Activation de la surveillance en même temps que vous configurez un nouveau pool Skype entreprise Server. (Dans Skype entreprise Server, la surveillance est activée ou désactivée sur la base d’un pool par pool.) Notez que vous pouvez activer le contrôle pour un pool sans réellement collecter les données de surveillance, processus expliqué dans la section Configuration de l’enregistrement des détails des appels et de la qualité de l’enregistrement de cette documentation.

2. Association d’un magasin d’analyse (c’est-à-dire une base de données de surveillance) au nouveau pool. Notez qu’un seul magasin d’analyse peut être associé à plusieurs pools. Selon le nombre d’utilisateurs hébergés sur vos pools de serveurs d’inscriptions, cela signifie que vous n’avez pas besoin de configurer une base de données de surveillance distincte pour chacun de vos pools. Un seul magasin d’analyse peut être utilisé par plusieurs pools.

Bien qu’il soit souvent plus simple d’activer la surveillance en même temps que vous créez un nouveau pool, il est également possible de créer un nouveau pool en désactivant la surveillance. Dans ce cas, vous pouvez ultérieurement utiliser le Générateur de topologie pour activer le service : le Générateur de topologie permet d’activer ou de désactiver la surveillance pour un pool ou d’associer un pool à un magasin d’analyse différent. N’oubliez pas que même si le rôle Serveur de surveillance n’existe plus, vous devez toujours créer un ou plusieurs magasins d’analyse : des bases de données principales utilisées pour stocker les données collectées par le service de surveillance. Ces bases de données principales peuvent être créées avec Microsoft SQL Server 2008 R2, Microsoft SQL Server 2012 ou Microsoft SQL Server 2014.

> [!NOTE]
> Si la surveillance a été activée pour un pool, vous pouvez désactiver le processus de collecte des données d’analyse sans avoir à modifier votre topologie : Skype entreprise Server vous permet de désactiver (puis de réactiver ultérieurement) les enregistrements des détails des appels (CDR) ou la qualité de Collection de données de l’utilisateur. Pour plus d’informations, voir la section Configuration de l’enregistrement des détails des appels et de la qualité de l’expérience de ce document.

Une autre amélioration importante apportée à l’analyse dans Skype entreprise Server réside dans le fait que les rapports de surveillance de Skype entreprise Server prennent désormais en charge le protocole IPv6 : les rapports qui utilisent le champ IP address affichent des adresses IPv4 ou IPv6 en fonction de : 1) la requête SQL en cours d’utilisation ; et 2) lorsque l’adresse IPv6 est stockée dans la base de données de surveillance.

> [!NOTE]
> Assurez-vous que le type de démarrage du service d’agent SQL Server est Automatique et que le service d’agent SQL Server est en cours d’exécution pour l’instance SQL qui contient les bases de données de surveillance, de sorte que les tâches de maintenance de surveillance par défaut de SQL Server peuvent s’exécuter selon leur planification sous le contrôle du service d’agent SQL Server.

Cette documentation vous guide tout au long du processus d’installation et de configuration de rapports de surveillance et de surveillance de Skype entreprise Server. La documentation donne des instructions détaillées qui vous aideront à effectuer les opérations suivantes :

- activer la surveillance dans votre topologie et associer un magasin d’analyse à un pool frontal ;

- Installez SQL Server Reporting Services et les rapports de surveillance de Skype entreprise Server. Les rapports de surveillance sont des rapports préconfigurés qui permettent de visualiser différemment les informations stockées dans une base de données de surveillance ;

- configurer la collecte des données de l’enregistrement des détails des appels ou de la qualité de l’expérience (QoE) de données. L’enregistrement des détails des appels vous permet d’effectuer le suivi de l’utilisation des fonctionnalités de Skype entreprise Server telles que les appels vers des téléphones VoIP. messagerie instantanée ; transferts de fichiers ; conférences audio/vidéo (A/V); et des sessions de partage d’application. Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et la « gigue » (différences de retard des paquets) ;

- vider manuellement les enregistrements des détails des appels et/ou QoE de la base de données de surveillance.

## <a name="deployment-checklist-for-monitoring"></a>Liste de vérification du déploiement pour la surveillance

Même si la surveillance est déjà installée et activée sur chaque serveur frontal, il existe toujours plusieurs étapes que vous devez effectuer avant de pouvoir réellement collecter les données de surveillance de Skype entreprise Server. Ces étapes sont décrites dans la liste de vérification suivante :

|**Phase**|**Étapes**|**Rôles et appartenance aux groupes**|**Documentation**|
|:-----|:-----|:-----|:-----|
|**Installer le matériel et les logiciels prérequis** <br/> |Installez une version prise en charge de Microsoft SQL Server sur l’ordinateur qui fera office de magasin de données principal pour la surveillance.  <br/> |Utilisateur de domaine qui est également membre du groupe Administrateurs local.  <br/> |[Supported Hardware](https://technet.microsoft.com/library/5f9c085d-205e-4235-9061-9ad875283cb0.aspx) <br/> [Server Software and Infrastructure Support](https://technet.microsoft.com/library/4ee5fe38-0191-4710-9aa2-df8895e8c51b.aspx) <br/> |
|**Créer la topologie interne appropriée pour prendre en charge la surveillance** <br/> |Utilisez le générateur de topologie Skype entreprise Server pour ajouter des bases de données de surveillance à la topologie, puis publiez la topologie mise à jour.  <br/> |Pour définir une topologie, utilisateur membre du groupe Utilisateurs local.  <br/> Pour publier la topologie, utilisateur membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.  <br/> |[Associez un magasin d’analyse à un pool frontal dans Skype entreprise Server](associate-a-monitoring-store.md) <br/> |
|**Activer les paramètres de surveillance appropriés** <br/> |Activez l’enregistrement des détails des appels et/ou la surveillance QoE au niveau des étendues Globale et/ou Site.  <br/> |Utilisateur membre du groupe RTCUniversalServerAdmins ou disposant d’un rôle RBAC qui permet d’accéder aux applets de commande CsCdrConfiguration et CsQoEConfiguration.  <br/> |[Configurer les paramètres d’enregistrement des détails des appels et de qualité de l’expertise dans Skype entreprise Server](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>Activer l’analyse

Bien que les agents de collecte des données unifiées soient automatiquement installés et activés sur chaque serveur frontal, cela signifie que vous commencerez automatiquement à collecter des données d’analyse à l’issue de l’installation de Skype entreprise Server. À la place, vous devez effectuer les deux actions suivantes : vous devez associer votre serveur frontal/les listes frontales à une base de données de surveillance, et vous devez activer l’enregistrement des détails des appels (CDR) et/ou la qualité de l’expertise (QoE) sur l’étendue globale et/ou l’étendue du site.

Pour obtenir des instructions pas à pas sur l’utilisation d’un serveur frontal ou d’une base de données de surveillance, voir la rubrique [associer un magasin d’analyse à un pool frontal dans Skype entreprise Server](associate-a-monitoring-store.md) dans le Guide de déploiement. Une fois ces associations créées et après la publication de votre nouvelle topologie de Skype entreprise Server, vous ne pourrez toujours pas collecter les données de surveillance. C’est pourquoi, par défaut, la collecte des données CDR et QoE est désactivée lors de l’installation de Skype entreprise Server.

Pour commencer la collecte de données, vous devez activer le contrôle CDR et/ou QoE. (Notez que vous n’avez pas besoin d’activer les contrôles CDR et QoE ; si vous le souhaitez, vous pouvez activer un seul type d’analyse tout en laissant l’autre type désactivé.) Pour activer le contrôle CDR dans le cadre global, exécutez la commande suivante à partir de Skype entreprise Server Management Shell :

```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Vous pouvez également activer le contrôle des CDR dans le panneau de configuration Skype entreprise Server. Dans le panneau de configuration Skype entreprise Server, procédez comme suit :

1. Cliquez sur **surveillance**.

2. Dans l’onglet **enregistrement des détails des appels** , double-cliquez sur le paramètre **Global** .

3. Dans le volet **modifier les paramètres d’enregistrement des détails des appels (CdR)** , sélectionnez **activer l’analyse de CDR** , puis cliquez sur **valider**.

Pour activer le contrôle QoE au niveau de l’étendue globale, exécutez la commande suivante à partir de Skype entreprise Server Management Shell :

```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

Si vous le souhaitez, vous pouvez également activer le contrôle QoE dans le panneau de configuration Skype entreprise Server. Dans le panneau de configuration, procédez comme suit :

1. Cliquez sur **surveillance**.

2. Sous l’onglet **données de qualité de l’environnement** , double-cliquez sur le paramètre **Global** .

3. Dans le volet des **paramètres de modification de la qualité de l’utilisation** , sélectionnez **activer l’analyse des données QoE** , puis cliquez sur **valider**.

Comme indiqué précédemment, les exemples précédents permettent de surveiller au niveau de l’étendue globale ; en d’autres, ils autorisent le contrôle CDR et QoE au sein de votre organisation. Vous pouvez également créer des paramètres de configuration de CDR et QoE séparés sur l’étendue du site, puis activer ou désactiver de manière sélective le contrôle de chaque site. Par exemple, vous pouvez activer le contrôle de CDR pour votre site de Redmond, mais désactiver le contrôle CDR pour votre site de Dublin. Pour plus d’informations sur la gestion de vos paramètres de configuration de la surveillance, voir le Guide de déploiement [configurer les paramètres d’enregistrement des détails des appels et de qualité de l’utilisation dans Skype entreprise Server](call-detail-recording-and-qoe.md).

## <a name="see-also"></a>Voir aussi

[Planifier l’analyse dans Skype entreprise Server](../../plan-your-deployment/monitoring.md)
