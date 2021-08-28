---
title: Processus de déploiement de Response Group dans Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Processus de déploiement et étapes pour Response Group dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 1cb85ac95025b71de8a071758befb5287a6fafa4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620180"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>Processus de déploiement de Response Group dans Skype Entreprise

Processus de déploiement et étapes pour Response Group dans Skype Entreprise Server Voix Entreprise.

Response Group est une fonctionnalité Voix Entreprise qui route et place en file d’attente les appels entrants vers des groupes de personnes, appelés agents, tels qu’un service d’assistance ou un service clientèle.

Les composants nécessaires à Response Group sont installés et activés automatiquement sur le serveur frontal ou le serveur Standard Edition Server lorsque vous déployez Voix Entreprise. Pour rendre Response Group accessible aux utilisateurs, vous devez configurer des groupes d’agents, des files d’attente, puis des workflows. En outre, un administrateur Response Group peut déléguer la configuration d’un flux de travail existant à un gestionnaire Response Group, qui peut ensuite modifier et reconfigurer le flux de travail, ainsi que ses groupes d’agents et files d’attente associés.

Pour configurer les groupes Response Group, vous devez être membre d’au moins un des rôles d’administrateur suivants :

|**Groupe de sécurité Active Directory (1)** <br/> |Créer un flux de travail  <br/> |Assigner un responsable  <br/> |Créer/assigner des agents, files d’attente  <br/> |Créer/gérer des vacances et heures d’ouverture  <br/> |Activer/désactiver un flux de travail  <br/> |Configurer un flux de travail (réponse vocale interactive ou groupe de recherche)  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**CsResponseGroupAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsResponseGroupManager** <br/> ||√(2)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |
|**CsVoiceAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsServerAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsViewOnlyAdministrator** <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |

> [!NOTE]
> **(1)** Un objet utilisateur des services de domaine Active Directory doit être membre du groupe de sécurité Active Directory spécifié répertorié. Un administrateur ou un autre membre du groupe Active Directory délégué ayant les autorisations appropriées pour ajouter des utilisateurs à un groupe de sécurité (par exemple, Administrateur, Opérateurs de compte) doit ajouter un objet utilisateur au groupe ou au groupe de sécurité répertorié pour que l’utilisateur puisse effectuer les fonctions répertoriées. **(2)** Uniquement pour les flux de travail que le CsResponseGroupAdministrator a affectés au CsResponseGroupManager. **(3)** Un gestionnaire Response Group peut affecter un autre membre de CsResponseGroupManager à un flux de travail que le responsable actuel gère déjà. **(4)** CsViewOnlyAdministrator ne peut exécuter que des cmdlets verbe « Get ».

## <a name="response-group-configuration-prerequisites"></a>Conditions préalables à la configuration de Response Group

Response Group requiert les composants suivants :

- Service d’application

- Application Response Group

- Modules linguistiques

- Magasin de fichiers (pour conserver les fichiers audio)

- Services Web (inclut l’outil de configuration Response Group et la console de signature et de sortie des agents)

Tous ces composants sont installés par défaut lorsque vous déployez Voix Entreprise.

Vous devrez peut-être effectuer les tâches suivantes avant de configurer Response Group :

- Activez les utilisateurs pour Lync Server 2013 et Voix Entreprise.

- modifier un fichier de configuration pour être compatible avec les normes FIPS (Federal Information Processing Standard) ;

- modifier le classement de base de données afin de prendre en charge les caractères Yi, Meng et Zang pour les noms des files d’attente et des groupes d’agents.

### <a name="enabling-users"></a>Activation des utilisateurs

La première étape de la configuration de Response Group consiste à créer des groupes d’agents. Avant de pouvoir créer un groupe d’agents, vous devez activer les utilisateurs qui seront agents de Response Group pour Skype Entreprise et Voix Entreprise. L’activation des utilisateurs Skype Entreprise est généralement une étape du déploiement Êdition Entreprise serveur Édition Standard serveur. Pour plus d’informations sur l’activation des utilisateurs pour Skype Entreprise, voir [Enable or Disable Users for Lync Server 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server). L’activation des utilisateurs pour Voix Entreprise se déroule généralement lors d’une étape du déploiement de Voix Entreprise. Pour plus d’informations, voir [Enable users for Voix Entreprise in Skype Entreprise Server](enable-users-for-enterprise-voice.md).

### <a name="complying-with-fips-requirements"></a>Respect des normes FIPS

Cette section vous est applicable uniquement si votre entreprise doit se conformer aux normes FIPS (Federal Information Processing Standard).

Pour permettre une compatibilité avec la norme FIPS, vous devez modifier le fichier d’application Web.config afin d’utiliser un algorithme de chiffrement différent après l’installation des services web. Vous devez préciser le recours à l’algorithme de chiffrement triple 3DES (Triple Data Encryption Standard) pour qu’ASP.NET puisse traiter les données ViewState. Pour l’application Response Group, cette exigence s’applique à l’outil de configuration Response Group et à la console de signature et de sortie de l’agent. Pour plus d’informations sur cette exigence, consultez l’article 911722 de la Base de connaissances Microsoft, « Vous pouvez recevoir un message d’erreur lorsque vous accédez à des pages web ASP.NET dont ViewState est activé après la mise à niveau de ASP.NET 1.1 vers ASP.NET 2.0 », à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183) .

Pour modifier le fichier Web.config, procédez comme suit :

1. Dans un éditeur de texte tel que le Bloc-Notes, ouvrez le fichier d’application Web.config.

2. Dans le Web.config, recherchez la  `<system.web>` section.

3. Ajoutez la  `<machineKey>` section suivante à la section `<system.web>` :

   ```xml
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Enregistrez le fichier Web.config.

5. Redémarrez le service Internet Information Services (IIS) en exécutant la commande suivante à une invite de commandes :

   ```console
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Prise en charge des caractères Yi, Meng et Zang

Cette section vous est applicable seulement si votre organisation doit prendre en charge les caractères Yi, Meng ou Zang.

> [!NOTE]
> Pour plus d’informations sur les caractères Yi, Meng et Zang et sur la raison pour laquelle ils peuvent être importants pour votre déploiement, voir les informations sur les jeux de caractères GB18030 [https://go.microsoft.com/fwlink/p/?linkId=240223](/previous-versions/sql/sql-server-2008-r2/ms180991(v=sql.105)) .

Pour la prise en charge des caractères Yi, Meng ou Zang, vous devez modifier le classement de la base de données Rgsconfig. Modifiez le classement de la colonne **Nom** des tableaux suivants dans chaque base de données Rgsconfig :

- dbo. AgentGroups

- dbo. BusinessHours

- dbo. HolidaySets

- dbo. Files d’attente

- dbo. Flux de travail

Pour SQL Server 2008 R2 et SQL Server 2012, utilisez le classement Latin_General_100 (sensible aux accents). Si vous utilisez ce classement, tous les noms d’objets ne tiennent pas compte de la casse.

Vous pouvez modifier le classement à l’aide de Microsoft SQL Server Management Studio. Pour plus d’informations sur l’utilisation de cet outil, voir [« Utilisation SQL Server Management Studio](/sql/ssms/sql-server-management-studio-ssms)». Pour modifier le classement, procédez comme suit :

1. Assurez-vous que SQL Server Management Studio est configuré pour autoriser les modifications nécessaires à la recréation des tables. Pour plus d’informations, voir « Boîte de dialogue Enregistrer [(non autorisé)](/sql/ssms/visual-db-tools/save-not-permitted-dialog-box)». Pour plus d’informations sur la définition d’un classement de colonne, voir « [How to: Set Column Collation (Visual Database Tools)](/previous-versions/sql/sql-server-2008-r2/ms187473(v=sql.105))».

2. À l’aide de Microsoft SQL Server Management Studio, connectez-vous à la base de données Rgsconfig.

3. Recherchez la table à modifier dans la base de données Rgsconfig, cliquez avec le bouton droit sur la table et cliquez sur **Conception**.

4. Modifiez le classement de la colonne **Nom** et enregistrez la table.

## <a name="response-group-deployment-steps"></a>Étapes de déploiement de Response Group

**Processus de déploiement de Response Group**

|**Étape**|**Étapes**|**Autorisations**|**Documentation de déploiement**|
|:-----|:-----|:-----|:-----|
|Activer les utilisateurs pour Skype Entreprise et pour Voix Entreprise  <br/> |Activez les utilisateurs qui seront des agents pour Skype Entreprise et Voix Entreprise. Les utilisateurs doivent être activés pour pouvoir être ajoutés aux groupes d’agents. En règle générale, les utilisateurs sont activés Skype Entreprise pendant le déploiement Êdition Entreprise ou Édition Standard serveur. Les utilisateurs sont activés pour Voix Entreprise pendant le Voix Entreprise déploiement.  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Activer ou désactiver les utilisateurs pour Lync Server 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server) <br/> [Activer les utilisateurs pour Voix Entreprise dans Skype Entreprise Server](enable-users-for-enterprise-voice.md) <br/> |
|Créer et configurer les groupes Response Group, qui sont composés de groupes d’agents, de files d’attente et de flux de travail  <br/> |1. Utilisez le Panneau de Skype Entreprise Server ou Skype Entreprise Server Management Shell pour :  <br/> a. Créez et configurez des groupes d’agents.  <br/> b. Créez et configurez des files d’attente.  <br/> 2. Vous pouvez éventuellement utiliser Skype Entreprise Server Management Shell pour créer des heures ouvées et des congés response group prédéfinés.  <br/> 3. Utilisez l’outil de configuration Response Group ou Skype Entreprise Server Management Shell pour créer des flux de travail (groupe de recherche ou flux d’appels de réponse vocale interactive( IVR), y compris les heures d’ouverture et les congés des groupes Response Group personnalisés.  <br/> Vous pouvez accéder à l’outil de configuration Response Group via Skype Entreprise Server Panneau de configuration.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[Créer des groupes d'agents Response Group](/previous-versions/office/lync-server-2013/lync-server-2013-create-response-group-agent-groups) <br/> [Créer des files d’attente Response Group](/previous-versions/office/lync-server-2013/lync-server-2013-create-response-group-queues) <br/> [(Facultatif) Définir les heures d’ouverture de Response Group dans Skype Entreprise](optional-define-response-group-business-hours.md) <br/> [(Facultatif) Définir des groupes de congés Response Group dans Skype Entreprise](optional-define-response-group-holiday-sets.md) <br/> [Conception et création de flux de travail Response Group dans Skype Entreprise](designing-and-creating-response-group-workflows.md) <br/> |
|(Facultatif) Personnaliser les paramètres au niveau de l’application  <br/> |Utilisez Skype Entreprise Server Management Shell pour personnaliser la configuration de l’attente musicale par défaut, le fichier audio d’attente musicale par défaut, la période de grâce de rappel de l’agent et la configuration du contexte de l’appel.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Gestion des paramètres Response Group au niveau de l’application dans Skype Entreprise](managing-application-level-response-group-settings.md) <br/> |
|(Facultatif) Déléguer la gestion des groupes Response Group  <br/> |Attribuez aux utilisateurs le rôle CsResponseGroupManager pour déléguer la configuration des groupes Response Group. Les responsables Response Group peuvent ensuite configurer les groupes Response Group qui leur sont affectés.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Planification du contrôle d’accès basé sur un rôle](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control) <br/> |
|Vérifier votre déploiement Response Group  <br/> |Testez la réponse aux appels des workflows de votre groupe de recherche et de votre système de réponse vocale interactive pour vérifier que la configuration fonctionne comme prévu.  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>Vue d’ensemble des scénarios de création de flux de travail

Lorsque vous créez des flux de travail, deux scénarios sont possibles :

- **L’administrateur crée et configure le flux de travail** — Le membre du rôle CsResponseGroupAdministrator (ou équivalent) crée et active le flux de travail et tous les éléments dans le flux de travail, tels que les groupes d’agents, les files d’attente, les congés et les heures ouvrées, la musique d’attente, etc.

- **L’administrateur crée le flux de travail et le responsable configure les options** — Le membre du rôle CsResponseGroupAdministrator (ou équivalent) définit l’URI SIP principal et le nom complet, affecte des membres du rôle CsResponseGroupManager, sélectionne une file d’attente et active le flux de travail. Le membre du rôle CsResponseGroupManager peut alors ouvrir une session et modifier la configuration du flux de travail en créant des groupes d’agents. Il affecte également le groupe à la file d’attente, configure le numéro de téléphone, les congés et les heures ouvrées, la musique d’attente, etc.

    > [!NOTE]
    > Lorsque vous voulez créer un flux de travail géré, vous devez créer le flux travail en tant que flux de travail actif. Après avoir enregistré un flux de travail géré et actif, vous pouvez le modifier et le désactiver.