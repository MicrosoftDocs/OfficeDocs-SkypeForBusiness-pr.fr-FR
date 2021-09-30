---
title: Configurer les ordinateurs Skype Entreprise Server qui seront surveillés
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 'Résumé : Installez les fichiers de l’agent Operations Manager sur l’ordinateur Skype Entreprise Server 2019 à surveiller et configurez l’ordinateur pour qu’il agisse en tant que proxy System Center serveur proxy.'
ms.openlocfilehash: bb8dce9edf44557632fc4e84188606152c76d646
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012178"
---
# <a name="configure-the-skype-for-business-server-computers-to-monitore"></a>Configurer les ordinateurs Skype Entreprise Server à surveiller

**Résumé :** Installez les fichiers de l’agent Operations Manager sur l’ordinateur Skype Entreprise Server 2019 à surveiller et configurez l’ordinateur pour qu’il agisse en tant que proxy System Center serveur.

Chaque Skype Entreprise Server 2019 que vous souhaitez surveiller doit être en mesure de signaler lui-même son existence au serveur de gestion. Pour activer ce processus, vous devez installer les fichiers de l’agent Operations Manager sur chacun des ordinateurs à surveiller. Après avoir installé les fichiers de l’agent, vous devez configurer l’ordinateur pour qu’il agisse en tant que proxy System Center serveur proxy. Assurez-vous que vous avez d’abord installé et configuré Skype Entreprise Server sur ces ordinateurs avant d’effectuer ces procédures.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Installation d’un certificat sur un nœud d’observation situé en dehors du réseau de périmètre
<a name="watcher_node_outside"> </a>

System Center Les agents Operations Manager qui s’exécutent dans un réseau de périmètre (tel qu’un serveur Edge Skype Entreprise Server), en dehors de l’entreprise (par exemple, un nœud d’observation des transactions synthétiques externes) ou à travers une limite d’confiance Active Directory, peuvent nécessiter la configuration d’un serveur de passerelle System Center Operations Manager. Ce rôle serveur permet aux agents qui n’ont pas de relation d’confiance avec le serveur d’administration racine de lever des alertes. Pour plus d’informations, voir [Managing Gateway Servers in Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh212823(v=sc.12)).

Si vous déployez un agent dans l’un de ces emplacements, vous devrez également demander et configurer un certificat qui permet au nœud watcher d’envoyer des alertes à System Center Operations Manager. Pour simplifier ce processus, l’équipe Operations Manager a créé un ensemble d’utilitaires qui vous permettent de demander et d’installer le type de certificat correct sur l’ordinateur du nœud observeur. Pour plus d’informations et pour télécharger ces [utilitaires,](https://techcommunity.microsoft.com/t5/system-center-blog/obtaining-certificates-for-non-domain-joined-agents-made-easy/ba-p/340467)voir Obtenir des certificats pour les agents non joints à un domaine facilité avec l’Assistant Génération de certificat.

### <a name="installing-the-operation-manager-agent-files"></a>Installation des fichiers de l’agent Operation Manager

1. Sur votre support System Center configuration, double-cliquez sur **Setup.exe**.

2. Dans l’System Center d’installation d’Operation Manager, cliquez sur **Installer l’agent Operations Manager,** à partir de l’agent d’installation sous Installations facultatives

3. Dans l System Center de configuration, dans la page Bienvenue dans l’Assistant Installation System Center Operations Manager, cliquez sur **Suivant.**

4. Dans la page Dossier de destination, sélectionnez le dossier dans lequel les fichiers de l’agent Operations Manager seront installés, puis cliquez sur **Suivant.**

5. Dans la page Configuration du groupe de gestion, **sélectionnez Spécifier les informations du groupe de gestion,** puis cliquez sur **Suivant.**

6. Dans la page Configuration du groupe de gestion, tapez le nom de votre groupe de gestion Operations Manager dans la zone Nom du groupe de gestion, puis tapez le nom d’hôte de votre serveur Operations Manager (par exemple, atl-scom-001) dans la zone **Serveur** d’administration.  Si vous avez modifié le numéro de port utilisé par Operations Manager, entrez le nouveau numéro de port dans la zone Port du serveur **d’administration.** Dans le cas contraire, laissez le port sur la valeur par défaut de 5723, puis cliquez sur **Suivant**.

7. Dans la page Compte d’action de l’agent, sélectionnez **Système local** et cliquez sur **Suivant**.

8. Dans la page Microsoft Update, sélectionnez Je ne souhaite pas utiliser **Microsoft Update** et cliquez sur **Suivant.**

9. Dans la page Prêt pour l'installation, cliquez sur **Installer**.

10. Dans la page Fin de l System Center d’installation d’Operations Manager, cliquez sur **Terminer.**

11. Cliquez sur **Quitter**.

Pour System Center 2012, vous pouvez vérifier que l’agent a été créé en cliquant sur **Démarrer,** sur Tous les **programmes,** sur **System Center Operations Manager 2012,** puis sur **Operations 2012 Manager Shell.** Dans la interpréteur de commandes d'Operations Manager, tapez la commande Windows PowerShell suivante, puis appuyez sur Entrée :
```PowerShell
Get-SCOMAgent
```

Une liste de tous vos agents Operations Manager s’affiche.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Configuration de l’ordinateur Skype Entreprise Server pour participer à la découverte System Center de données
<a name="watcher_node_outside"> </a>

Pour vous assurer que votre nouvel agent Skype Entreprise Server participe au processus de découverte pour System Center Operations Manager, vous devez effectuer la procédure suivante sur chaque ordinateur sur lequel la console System Center Operations Manager a été installée :

1. Sous l’onglet Administration, cliquez sur **Géré par agent**.

2. Cliquez sur **l’Assistant Découverte** et terminez l’Assistant pour l’ordinateur à découvrir.

3. Redémarrez le service d’agent d’état d’santé. Le redémarrage du service force la découverte du nouvel ordinateur. Si vous ne redémarrez pas le service, cela peut prendre jusqu’à 4 heures avant que le nouvel ordinateur ne soit découvert par System Center Operations Manager.

4. Vérifiez qu’aucun événement d’erreur n’a été enregistré dans le journal des événements Operations Manager.

5. L’ordinateur sur lequel l’agent a été poussée s’affiche sous la liste « Géré par l’agent » et l’ordinateur sur lequel l’agent a été installé manuellement s’affiche sous « Gestion en attente », cliquez sur le nom de l’ordinateur et approuvez.

6. Cliquez avec le bouton droit sur le nom de l’ordinateur, puis cliquez sur **Propriétés**. Dans la boîte de dialogue Propriétés, sous l’onglet Sécurité, sélectionnez **Autoriser cet agent à agir en tant que proxy et découvrir des objets gérés sur d’autres ordinateurs**, puis cliquez sur **OK**.