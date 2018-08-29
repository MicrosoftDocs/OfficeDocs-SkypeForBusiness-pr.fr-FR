---
title: Déployer la surveillance dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 'Résumé : Découvrez comment déployer la surveillance dans Skype pour Business Server.'
ms.openlocfilehash: 0bcc324e9f37b37078719e3e5c0e5ffe1518f5cd
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252386"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>Déployer la surveillance dans Skype pour Business Server

**Résumé :** Découvrez comment déployer la surveillance dans Skype pour Business Server.

Avant d’effectuer ces tâches, consultez [Plan pour la surveillance dans Skype pour Business Server](../../plan-your-deployment/monitoring.md).

Vous implémenterez généralement les services de surveillance au sein de votre topologie en effectuant les deux étapes suivantes :

1. Activation de la surveillance en même temps vous configurer un nouveau Skype pour le pool de serveurs d’entreprise. (Dans Skype pour Business Server, de surveillance est activé ou désactivé selon le pool par pool.) Notez que vous pouvez activer la surveillance pour un pool sans réellement collecte des données de surveillance, un processus indiqué dans la section Configuration de l’enregistrement des détails des appels et des paramètres de qualité de l’expérience de cette documentation.

2. Association d’un magasin d’analyse (c’est-à-dire une base de données de surveillance) au nouveau pool. Notez qu’un seul magasin d’analyse peut être associé à plusieurs pools. Selon le nombre d’utilisateurs hébergés sur vos pools de serveurs d’inscriptions, cela signifie que vous n’avez pas besoin de configurer une base de données de surveillance distincte pour chacun de vos pools. Un seul magasin d’analyse peut être utilisé par plusieurs pools.

Bien qu’il soit souvent plus simple d’activer la surveillance en même temps que vous créez un nouveau pool, il est également possible de créer un nouveau pool en désactivant la surveillance. Dans ce cas, vous pouvez ultérieurement utiliser le Générateur de topologie pour activer le service : le Générateur de topologie permet d’activer ou de désactiver la surveillance pour un pool ou d’associer un pool à un magasin d’analyse différent. N’oubliez pas que même si le rôle Serveur de surveillance n’existe plus, vous devez toujours créer un ou plusieurs magasins d’analyse : des bases de données principales utilisées pour stocker les données collectées par le service de surveillance. Ces bases de données principales peuvent être créées avec Microsoft SQL Server 2008 R2, Microsoft SQL Server 2012 ou Microsoft SQL Server 2014.

> [!NOTE]
> Si le contrôle a été activé pour un pool, vous pouvez désactiver le processus de collecte des données de surveillance sans devoir modifier votre topologie : Skype pour Business Server fournit un moyen de désactiver (et réactiver) appel d’enregistrement des détails ou qualité de Collecte de données de l’expérience (QoE). Pour plus d’informations, voir la section Configuration de l’enregistrement des détails des appels et de la qualité de l’expérience de ce document.

Une autre amélioration importante à la surveillance dans Skype pour Business Server est le fait que Skype pour les rapports de surveillance Business Server prennent désormais en charge IPv6 : rapports qui utilisent le champ adresse IP affichera IPv4 ou en fonction des adresses IPv6 : 1) la requête SQL utilisé ; et, 2) où ou non l’adresse IPv6 est stocké dans la base de données de surveillance.

> [!NOTE]
> Assurez-vous que le type de démarrage du service d’agent SQL Server est Automatique et que le service d’agent SQL Server est en cours d’exécution pour l’instance SQL qui contient les bases de données de surveillance, de sorte que les tâches de maintenance de surveillance par défaut de SQL Server peuvent s’exécuter selon leur planification sous le contrôle du service d’agent SQL Server.

Cette documentation vous guide tout au long du processus d’installation et configuration des rapports de surveillance et de surveillance pour Skype pour Business Server. La documentation donne des instructions détaillées qui vous aideront à effectuer les opérations suivantes :

- activer la surveillance dans votre topologie et associer un magasin d’analyse à un pool frontal ;

- Installez SQL Server Reporting Services et le Skype pour Business Server rapports de surveillance. Les rapports de surveillance sont des rapports préconfigurés qui permettent de visualiser différemment les informations stockées dans une base de données de surveillance ;

- configurer la collecte des données de l’enregistrement des détails des appels ou de la qualité de l’expérience (QoE) de données. Enregistrement des détails des appels offre un moyen pour effectuer le suivi de l’utilisation de Skype pour les fonctionnalités de Business Server telles que les voix sur IP (VoIP) appels ; messagerie instantanée (IM) ; transferts de fichiers ; audio/vidéo (A / V) conférence ; et les sessions de partage d’application. Les mesures de la qualité de l’expérience (QoE) effectuent le suivi de la qualité des appels audio et vidéo dans votre organisation, y compris le nombre de paquets réseau perdus, le bruit de fond et la « gigue » (différences de retard des paquets) ;

- vider manuellement les enregistrements des détails des appels et/ou QoE de la base de données de surveillance.

## <a name="deployment-checklist-for-monitoring"></a>Liste de vérification du déploiement pour la surveillance

Bien que le contrôle est déjà installé et activé sur chaque serveur frontal, il y a encore plusieurs étapes que vous devez effectuer avant de pouvoir effectivement en cours pour recueillir des données d’analyse pour Skype pour Business Server. Ces étapes sont décrites dans la liste de vérification suivante :

|**Phase**|**Étapes**|**Rôles et appartenance aux groupes**|**Documentation**|
|:-----|:-----|:-----|:-----|
|**Installer le matériel et les logiciels prérequis** <br/> |Installez une version prise en charge de Microsoft SQL Server sur l’ordinateur qui fera office de magasin de données principal pour la surveillance.  <br/> |Utilisateur de domaine qui est également membre du groupe Administrateurs local.  <br/> |[Matériel pris en charge](https://technet.microsoft.com/library/5f9c085d-205e-4235-9061-9ad875283cb0.aspx) <br/> [Server Software and Infrastructure Support](https://technet.microsoft.com/library/4ee5fe38-0191-4710-9aa2-df8895e8c51b.aspx) <br/> |
|**Créer la topologie interne appropriée pour prendre en charge la surveillance** <br/> |Utiliser Skype pour le Générateur de topologie Business Server ajouter surveillance des bases de données de la topologie, puis publiez la topologie mise à jour.  <br/> |Pour définir une topologie, utilisateur membre du groupe Utilisateurs local.  <br/> Pour publier la topologie, utilisateur membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.  <br/> |[Associer un pool frontal dans Skype pour Business Server dans un magasin d’analyse](associate-a-monitoring-store.md) <br/> |
|**Activer les paramètres de surveillance appropriés** <br/> |Activez l’enregistrement des détails des appels et/ou la surveillance QoE au niveau des étendues Globale et/ou Site.  <br/> |Utilisateur membre du groupe RTCUniversalServerAdmins ou disposant d’un rôle RBAC qui permet d’accéder aux applets de commande CsCdrConfiguration et CsQoEConfiguration.  <br/> |[Configurer un enregistrement des détails des appels et les paramètres de qualité de l’expérience dans Skype pour Business Server](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>Activer la surveillance

Bien que les agents de collecte de données unifié sont automatiquement installés et activés sur chaque serveur frontal, cela ne signifie pas que vous commencera automatiquement à collecter des données d’analyse au moment où que vous avez terminé l’installation Skype pour Business Server. Auparavant, vous devez associer vos serveurs frontaux/pools frontaux à une base de données de surveillance et vous devez activer la surveillance des enregistrements des détails des appels et/ou la surveillance des données de qualité de l’expérience au niveau de l’étendue globale et/ou de l’étendue du site.

Pour obtenir des instructions sur l’association de serveurs frontaux ou des pools frontaux avec une base de données de surveillance, consultez la rubrique [associer un magasin de surveillance avec un pool frontal dans Skype pour Business Server](associate-a-monitoring-store.md) dans le guide de déploiement. Une fois ces associations ont été apportées, et une fois votre nouveau Skype pour la topologie du serveur d’entreprise a été publié, vous toujours pas sera en mesure de collecter des données d’analyse. C’est parce que, par défaut, la collecte de données CDR et QoE est désactivé lorsque vous installez Skype pour Business Server.

Afin de pouvoir commencer la collecte de données, vous devez activer la surveillance des enregistrements des détails des appels et/ou la surveillance des données de qualité de l’expérience. (Notez que vous ne possèdent pas d’activer les deux des détails des appels et la surveillance QoE ; si vous préférez, vous pouvez activer un type de surveillance tout en laissant l’autre type désactivé). Pour activer la surveillance, à l’exécution de l’étendue globale, la commande suivante à partir de la Skype pour Business Server Management Shell des détails des appels :

```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Autrement, vous pouvez activer CDR analyse à partir de dans la Skype pour le panneau de configuration serveur Business. À partir de dans la Skype pour Business Server Control Panel, procédez comme suit :

1. Cliquez sur **Surveillance**.

2. Sous l’onglet **Enregistrement des détails des appels**, double-cliquez sur le paramètre **Global**.

3. Dans le volet **Paramètre de l’enregistrement des détails des appels (CDR)**, sélectionnez **Activer la surveillance des enregistrements des détails des appels**, puis cliquez sur **Valider**.

Pour activer la surveillance QoE au niveau de l’étendue globale, exécutez cette commande à partir de la Skype pour Business Server Management Shell :

```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

Si vous préférez, vous pouvez également activer la surveillance de QoE à partir de dans la Skype pour le panneau de configuration serveur Business. Dans le Panneau de configuration, effectuez la procédure suivante :

1. Cliquez sur **Surveillance**.

2. Sous l’onglet **Données de qualité de l’expérience**, double-cliquez sur le paramètre **Global**.

3. Dans le volet **Paramètre de qualité de l’expérience (QoE)**, sélectionnez **Activer la surveillance des données de qualité de l’expérience**, puis cliquez sur **Valider**.

Comme indiqué, les exemples précédents activent la surveillance au niveau de l’étendue globale ; ils activent les surveillances CDR et QoE dans toute votre organisation. Vous pouvez également créer des paramètres de configuration CDR et QoE distincts au niveau de l’étendue du site, puis activer ou désactiver de façon sélective la surveillance pour chaque site. Par exemple, vous pouvez activer la surveillance CDR pour votre site de Redmond et la désactiver pour votre site de Dublin. Pour plus d’informations sur la gestion de vos paramètres de configuration de surveillance, voir la rubrique [Configure appeler l’enregistrement des détails et les paramètres de qualité de l’expérience dans Skype pour Business Server](call-detail-recording-and-qoe.md)du guide de déploiement.

## <a name="see-also"></a>Voir aussi

[Planifier la surveillance dans Skype pour Business Server](../../plan-your-deployment/monitoring.md)