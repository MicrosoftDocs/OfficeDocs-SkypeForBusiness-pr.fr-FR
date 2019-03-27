---
title: Configuration des ordinateurs Skype Entreprise Server qui seront surveillés
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: 'Résumé : Installez les fichiers de l’agent Operations Manager sur le Skype pour ordinateur Business Server 2015 à surveiller et configurer l’ordinateur d’agir comme un proxy de System Center.'
ms.openlocfilehash: 55d862517eeaad6fbfb567fe4327c375fc1ce2e1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895019"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>Configuration des ordinateurs Skype Entreprise Server qui seront surveillés

**Résumé :** Installer les fichiers de l’agent Operations Manager sur le Skype pour ordinateur Business Server 2015 à surveiller et configurer l’ordinateur d’agir comme un proxy de System Center.

Chaque Skype pour ordinateur Business Server 2015 dont vous souhaitez surveiller doit pouvoir automatique signaler son existence au serveur d’administration. Pour cela, vous devez installer les fichiers d’agent Operations Manager sur chacun des ordinateurs à surveiller. Une fois les fichiers d’agent installés, vous devez configurer l’ordinateur de sorte qu’il assume la fonction de proxy System Center. N’oubliez pas que vous avez installé et configuré en premier Skype pour Business Server sur ces ordinateurs avant d’effectuer ces procédures.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Installation d’un certificat sur un nœud observateur situé en dehors du réseau de périmètre
<a name="watcher_node_outside"> </a>

Les agents System Center Operations Manager en cours d’exécution dans un périmètre de réseau (par exemple, Skype pour Business Server Edge) en dehors de l’entreprise (par exemple un nœud Observateur de transaction synthétique externe) ou sur une approbation Active Directory limite, peut nécessiter la configuration d’un serveur de passerelle de System Center Operations Manager. Ce rôle serveur permet aux agents qui n’ont pas de relation d’approbation avec le serveur d’administration racine de déclencher des alertes. Pour plus d’informations, voir [Gestion des serveurs de passerelle dans Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).

Si vous déployez un agent dans un de ces emplacements, vous devez également demander et configurer un certificat qui permet le nœud Observateur envoyer des alertes pour System Center Operations Manager. Pour simplifier ce processus, l’équipe Operations Manager a créé un ensemble d’utilitaires qui vous permettent de demander et installer le type de certificat approprié sur l’ordinateur nœud Observateur. Pour plus d’informations et pour télécharger ces utilitaires, voir [Obtention de certificats pour le domaine lié Agents Made Easy avec l’Assistant génération de certificat](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).

### <a name="installing-the-operation-manager-agent-files"></a>Installation des fichiers de l’agent Operation Manager

1. Dans votre support d’installation System Center, double-cliquez sur **Setup.exe**.

2. Dans l’Assistant Installation de System Center Operation Manager, cliquez sur **Installer l’Agent Operations Manager**, à partir de l’installation de l’Agent sous Installations facultatif

3. Dans l’Assistant Installation de System Center, sur la Bienvenue dans la page Assistant Installation de System Center Operations Manager, cliquez sur **suivant**.

4. Dans la page dossier de Destination, sélectionnez le dossier où les fichiers de l’Agent Operations Manager seront installés et cliquez sur **suivant**.

5. Dans la page Configuration du groupe d’administration, sélectionnez **Spécifier les informations du groupe d’administration**, puis cliquez sur **Suivant**.

6. Dans la page Configuration du groupe gestion, tapez le nom de votre groupe d’administration Operations Manager dans la zone **Nom de groupe d’administration** , puis tapez le nom d’hôte de votre serveur Operations Manager (par exemple, atl-scom-001) dans le serveur de gestion ** **zone. Si vous avez modifié le numéro de port utilisé par Operations Manager, tapez le nouveau numéro de port dans la zone **Port de serveur d’administration**. Sinon, laissez la valeur par défaut sur 5723, puis cliquez sur **Suivant**.

7. Dans la page Compte d’action d’agent, sélectionnez **Système local**, puis cliquez sur **Suivant**.

8. Dans la page Microsoft Update, sélectionnez **Je ne souhaite pas utiliser Microsoft Update**, puis cliquez sur  **Suivant**.

9. Dans la page Prêt pour l’installation, cliquez sur **Installer**.

10. Sur la fin de la page Assistant Installation de System Center Operations Manager, cliquez sur **Terminer**.

11. Cliquez sur **Quitter**.

Pour System Center 2012, vous pouvez vérifier que l’agent a été créé en cliquant sur **Démarrer**, sur **Tous les programmes**, cliquez sur **System Center Operations Manager 2012**, puis en cliquant sur **Interface d’Operations Manager 2012**. In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:
```
Get-SCOMAgent
```

Une liste de tous vos agents Operations Manager apparaît.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Configuration de l’ordinateur Skype Entreprise Server pour la participation à la découverte de System Center
<a name="watcher_node_outside"> </a>

Pour vous assurer que votre nouveau Skype pour l’agent Business Server participe au processus de découverte de System Center Operations Manager, vous devez effectuer la procédure suivante sur chaque ordinateur sur lequel la console System Center Operations Manager est installée :

1. Sous l’onglet Administration, cliquez sur **Géré par agent**.

2. Cliquez sur **Assistant de découverte** et exécutez l’Assistant pour l’ordinateur à découvrir.

3. Redémarrez le service de l’agent d’intégrité. Le redémarrage du service va forcer la découverte du nouvel ordinateur. Si vous ne pas redémarrez le service, il peut prendre jusqu'à 4 heures avant le nouvel ordinateur est détecté par System Center Operations Manager.

4. Vérifiez qu’aucun événement d’erreur n’a été enregistré dans le journal des événements Operations Manager.

5. L’ordinateur où l’agent est expédié avec succès sera affichée sous la liste « Géré par Agent » et l’ordinateur sur lequel l’agent a été installé manuellement sera affichée sous « Gestion en attente », cliquez sur le nom d’ordinateur et d’approuver.

6. Cliquez avec le bouton droit sur le nom de l’ordinateur, puis cliquez sur **Propriétés**. Dans la boîte de dialogue Propriétés, sous l’onglet Sécurité, sélectionnez **Autoriser cet agent à agir en tant que proxy et découvrir des objets gérés sur d’autres ordinateurs**, puis cliquez sur **OK**.


