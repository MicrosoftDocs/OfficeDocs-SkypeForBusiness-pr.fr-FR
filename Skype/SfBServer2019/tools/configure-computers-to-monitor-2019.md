---
title: Configurer les ordinateurs Skype entreprise Server qui seront surveillés
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé : Installez les fichiers de l’agent Operations Manager sur l’ordinateur Skype entreprise Server 2019 à surveiller et configurez l’ordinateur pour qu’il se comporte comme un proxy System Center.'
ms.openlocfilehash: a79101a80fd68eb7b65b7f981874afa44f5cb5f3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006059"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>Configurer les ordinateurs Skype entreprise Server qui seront surveillés

**Résumé :** Installez les fichiers de l’agent Operations Manager sur l’ordinateur Skype entreprise Server 2019 à surveiller et configurez l’ordinateur pour qu’il agisse comme un proxy System Center.

Chaque ordinateur Skype entreprise Server 2019 que vous souhaitez surveiller doit être en mesure de signaler lui-même son existence au serveur de gestion. Pour activer ce processus, vous devez installer les fichiers de l’agent Operations Manager sur chacun des ordinateurs à surveiller. Après avoir installé les fichiers de l’agent, vous devez configurer l’ordinateur pour qu’il se comporte comme un proxy System Center. Assurez-vous que vous avez préalablement installé et configuré Skype entreprise Server sur ces ordinateurs avant d’exécuter ces procédures.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Installation d’un certificat sur un nœud observateur situé en dehors du réseau de périmètre
<a name="watcher_node_outside"> </a>

Les agents System Center Operations Manager exécutés dans un réseau de périmètre (par exemple, un serveur Edge Skype entreprise Server), en dehors de l’entreprise (par exemple, un nœud observateur de transaction synthétique externe) ou dans une limite d’approbation Active Directory, peuvent nécessiter la configuration d’un serveur de passerelle System Center Operations Manager. Ce rôle de serveur permet aux agents qui n’ont pas de relation d’approbation avec le serveur d’administration racine de déclencher des alertes. Pour plus d’informations, consultez la rubrique [Managing Gateway servers in Operations Manager 2012](https://technet.microsoft.com/library/hh212823.aspx).

Si vous déployez un agent à l’un de ces emplacements, vous devrez également demander et configurer un certificat qui permet au nœud observateur d’envoyer des alertes à System Center Operations Manager. Pour simplifier ce processus, l’équipe Operations Manager a créé un ensemble d’utilitaires qui vous permettent de demander et d’installer le type correct de certificat sur l’ordinateur du nœud observateur. Pour plus d’informations et pour télécharger ces utilitaires, reportez-vous à la rubrique [obtention de certificats pour des agents non joints à un domaine facilitée avec l’Assistant génération de certificat](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).

### <a name="installing-the-operation-manager-agent-files"></a>Installation des fichiers de l’agent Operation Manager

1. Sur le support d’installation de System Center, double-cliquez sur **Setup. exe**.

2. Dans l’Assistant Installation de System Center Operation Manager, cliquez sur **installer l’agent Operations Manager**, à partir de l’option installer l’agent sous installations facultatives.

3. Dans l’Assistant Installation de System Center, dans la page Bienvenue dans l’Assistant Installation de System Center Operations Manager, cliquez sur **suivant**.

4. Sur la page dossier de destination, sélectionnez le dossier dans lequel les fichiers de l’agent Operations Manager seront installés, puis cliquez sur **suivant**.

5. Dans la page Configuration du groupe d’administration, sélectionnez **spécifier les informations du groupe d’administration** , puis cliquez sur **suivant**.

6. Dans la page Configuration du groupe d’administration, tapez le nom de votre groupe d’administration Operations Manager dans la zone **nom du groupe d’administration** , puis tapez le nom d’hôte de votre serveur Operations Manager (par exemple, ATL-SCOM-001) dans la zone serveur d' **administration** . Si vous avez modifié le numéro de port utilisé par Operations Manager, entrez le nouveau numéro de port dans la zone **port du serveur d’administration** . Dans le cas contraire, laissez le port à la valeur par défaut 5723, puis cliquez sur **suivant**.

7. Sur la page compte d’action d’agent, sélectionnez **système local** , puis cliquez sur **suivant**.

8. Sur la page Microsoft Update, sélectionnez **je ne souhaite pas utiliser Microsoft Update** , puis cliquez sur **suivant**.

9. Dans la page Prêt pour l'installation, cliquez sur **Installer**.

10. Sur la page fin de l’Assistant Installation de System Center Operations Manager, cliquez sur **Terminer**.

11. Cliquez sur **Quitter**.

Pour System Center 2012, vous pouvez vérifier que l’agent a bien été créé en cliquant sur **Démarrer**, puis sur **tous les programmes**, sur **System Center Operations Manager 2012**, puis sur **Operations 2012 Manager Shell**. Dans l’environnement de ligne de commande Operations Manager, tapez la commande Windows PowerShell suivante, puis appuyez sur entrée :
```PowerShell
Get-SCOMAgent
```

Une liste de tous vos agents Operations Manager s’affiche.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Configuration de l’ordinateur Skype entreprise Server pour la participation à la découverte de System Center
<a name="watcher_node_outside"> </a>

Pour vous assurer que votre nouvel agent Skype entreprise Server participe au processus de découverte de System Center Operations Manager, vous devez effectuer la procédure suivante sur chaque ordinateur sur lequel la console System Center Operations Manager a été installée :

1. Sous l’onglet Administration, cliquez sur **Géré par agent**.

2. Cliquez sur **Assistant de découverte** et terminez l’Assistant pour l’ordinateur à découvrir.

3. Redémarrez le service d’agent d’intégrité. Le redémarrage du service forcera la découverte du nouvel ordinateur. Si vous ne redémarrez pas le service, il peut prendre jusqu’à 4 heures avant la découverte de System Center Operations Manager.

4. Vérifiez qu’aucun événement d’erreur n’a été enregistré dans le journal des événements Operations Manager.

5. L’ordinateur sur lequel l’agent est exécuté correctement est affiché sous la liste « gérée par l’agent » et l’ordinateur sur lequel l’agent a été installé manuellement apparaît sous « gestion en attente », cliquez sur le nom de l’ordinateur et approuvez-le.

6. Cliquez avec le bouton droit sur le nom de l’ordinateur, puis cliquez sur **Propriétés**. Dans la boîte de dialogue Propriétés, sous l’onglet Sécurité, sélectionnez **Autoriser cet agent à agir en tant que proxy et découvrir des objets gérés sur d’autres ordinateurs**, puis cliquez sur **OK**.


