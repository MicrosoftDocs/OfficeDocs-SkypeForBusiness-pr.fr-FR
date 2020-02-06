---
title: Configuration des ordinateurs Skype Entreprise Server qui seront surveillés
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
description: 'Résumé : Installez les fichiers de l’agent Operations Manager dans l’ordinateur 2019 de Skype entreprise Server à surveiller, puis configurez l’ordinateur pour qu’il serve de proxy de centre système.'
ms.openlocfilehash: 4585903e4911ee6acf8121220677c66d0d8445fe
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824008"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>Configuration des ordinateurs Skype Entreprise Server qui seront surveillés

**Résumé :** Installez les fichiers de l’agent Operations Manager dans l’ordinateur 2019 de Skype entreprise Server à surveiller, puis configurez l’ordinateur pour qu’il serve de proxy de centre système.

Chaque ordinateur Skype entreprise Server 2019 que vous souhaitez surveiller doit être en mesure de signaler son existence au serveur de gestion. Pour cela, vous devez installer les fichiers d’agent Operations Manager sur chacun des ordinateurs à surveiller. Une fois les fichiers d’agent installés, vous devez configurer l’ordinateur de sorte qu’il assume la fonction de proxy System Center. Assurez-vous d’avoir installé et configuré Skype entreprise Server sur ces ordinateurs avant de procéder à ces procédures.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Installation d’un certificat sur un nœud observateur situé en dehors du réseau de périmètre
<a name="watcher_node_outside"> </a>

Les agents du gestionnaire d’opérations de System Center qui s’exécutent dans un réseau de périmètre (par exemple, un serveur Edge de Skype entreprise Server), en dehors de l’entreprise (par exemple, un nœud d’observateur de transactions synthétiques externes) ou sur une limite d’approbation Active Directory, nécessitent configuration d’un serveur de passerelle System Center Operations Manager. Ce rôle serveur permet aux agents qui n’ont pas de relation d’approbation avec le serveur d’administration racine de déclencher des alertes. Pour plus d’informations, reportez-vous [à gestion des serveurs de passerelles dans Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).

Si vous déployez un agent à l’un de ces emplacements, vous devrez également demander et configurer un certificat qui permet au nœud d’observation d’envoyer des alertes à System Center Operations Manager. Pour simplifier ce processus, l’équipe Operations Manager a créé un ensemble d’utilitaires qui vous permettent de demander et d’installer le type correct de certificat sur l’ordinateur de nœud d’observation. Pour plus d’informations, consultez l’aide de l’Assistant génération de certificats pour plus d’informations sur l' [obtention de certificats pour les agents non joints de domaines](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).

### <a name="installing-the-operation-manager-agent-files"></a>Installation des fichiers de l’agent Operation Manager

1. Dans votre support d’installation System Center, double-cliquez sur **Setup.exe**.

2. Dans l’Assistant Configuration de System Center Operation Manager, cliquez sur **installer l’agent Operations Manager**, à partir de l’agent d’installation sous installations facultatives

3. Dans l’Assistant Configuration de System Center, dans la page Bienvenue dans l’Assistant Configuration de System Center Operations Manager, cliquez sur **suivant**.

4. Dans la page dossier de destination, sélectionnez le dossier dans lequel les fichiers de l’agent Operations Manager seront installés, puis cliquez sur **suivant**.

5. Dans la page Configuration du groupe d’administration, sélectionnez **Spécifier les informations du groupe d’administration**, puis cliquez sur **Suivant**.

6. Dans la page Configuration du groupe de gestion, tapez le nom de votre groupe d’administration Operations Manager dans la zone **nom du groupe de gestion** , puis tapez le nom d’hôte de votre serveur Operations Manager (par exemple, ATL-SCOM-001) dans la zone serveur de **gestion** . Si vous avez modifié le numéro de port utilisé par Operations Manager, tapez le nouveau numéro de port dans la zone **Port de serveur d’administration**. Sinon, laissez la valeur par défaut sur 5723, puis cliquez sur **Suivant**.

7. Dans la page Compte d’action d’agent, sélectionnez **Système local**, puis cliquez sur **Suivant**.

8. Dans la page Microsoft Update, sélectionnez **Je ne souhaite pas utiliser Microsoft Update**, puis cliquez sur  **Suivant**.

9. Dans la page Prêt pour l’installation, cliquez sur **Installer**.

10. Dans la page fin de l’Assistant Configuration de System Center Operations Manager, cliquez sur **Terminer**.

11. Cliquez sur **Quitter**.

Pour System Center 2012, vous pouvez vérifier que l’agent a été créé en cliquant sur **Démarrer**, sur **tous les programmes**, sur **System Center Operations Manager 2012**, puis sur **Operations 2012 Manager Shell**. In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:
```PowerShell
Get-SCOMAgent
```

Une liste de tous vos agents Operations Manager apparaît.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Configuration de l’ordinateur Skype Entreprise Server pour la participation à la découverte de System Center
<a name="watcher_node_outside"> </a>

Pour vous assurer que votre nouvel agent Skype entreprise Server est impliqué dans le processus de découverte de System Center Operations Manager, vous devez effectuer la procédure suivante sur chaque ordinateur sur lequel la console System Center Operations Manager a été installée :

1. Sous l’onglet Administration, cliquez sur **Géré par agent**.

2. Cliquez sur **Assistant de découverte** et exécutez l’Assistant pour l’ordinateur à découvrir.

3. Redémarrez le service de l’agent d’intégrité. Le redémarrage du service va forcer la découverte du nouvel ordinateur. Si vous ne redémarrez pas le service, il peut s’écouler jusqu’à 4 heures avant la découverte du nouvel ordinateur par System Center Operations Manager.

4. Vérifiez qu’aucun événement d’erreur n’a été enregistré dans le journal des événements Operations Manager.

5. Sur l’ordinateur sur lequel l’agent est passé avec succès, la liste « géré par l’agent » s’affiche, dans la liste « gestion en attente », cliquez sur le nom de l’ordinateur et approuvez-le.

6. Cliquez avec le bouton droit sur le nom de l’ordinateur, puis cliquez sur **Propriétés**. Dans la boîte de dialogue Propriétés, sous l’onglet Sécurité, sélectionnez **Autoriser cet agent à agir en tant que proxy et découvrir des objets gérés sur d’autres ordinateurs**, puis cliquez sur **OK**.


