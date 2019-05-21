---
title: Processus de déploiement pour Response Group dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
description: Processus de déploiement et étapes pour le groupe réponse dans Skype entreprise Server voix entreprise.
ms.openlocfilehash: 62c6471018c3c1c6d1943d252975d2e671ef8cf4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275614"
---
# <a name="deployment-process-for-response-group-in-skype-for-business"></a>Processus de déploiement pour Response Group dans Skype entreprise

Processus de déploiement et étapes pour le groupe réponse dans Skype entreprise Server voix entreprise.

Response Group est une fonctionnalité de voix entreprise qui achemine et met en file d’attente les appels entrants vers des groupes de personnes, appelés agents, tels qu’un service d’assistance ou un service clientèle.

Les composants requis par le groupe de réponse sont installés et activés automatiquement sur le serveur frontal ou le serveur Standard Edition lors du déploiement de voix entreprise. Pour rendre le groupe de réponses disponible pour les utilisateurs, vous devez configurer des groupes d’agents, des files d’attente, puis des flux de travail. Par ailleurs, un administrateur de groupe de réponse peut déléguer la configuration d’un flux de travail existant à un gestionnaire de groupe de réponse, qui peut ensuite modifier et reconfigurer le flux de travail ainsi que ses groupes d’agents et files d’attente associés.

Pour configurer les groupes Response Group, vous devez être membre d’au moins l’un des rôles d’administrateur suivants :

|**Groupe de sécurité Active Directory (1)** <br/> |Création d’un flux de travail  <br/> |Affectation d’un responsable  <br/> |Création/Affectation des agents, des files d’attente  <br/> |Création/Gestion des congés et des heures d’ouverture  <br/> |Activation/Désactivation d’un flux de travail  <br/> |Configuration d’un flux de travail (réponse vocale interactive ou groupe de recherche)  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|**CsResponseGroupAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsResponseGroupManager** <br/> ||√(2)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |√(3)  <br/> |
|**CsVoiceAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsServerAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsAdministrator** <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |√  <br/> |
|**CsViewOnlyAdministrator** <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |√(4)  <br/> |

> [!NOTE]
> **(1)** un objet utilisateur des services de domaine Active Directory doit être membre du groupe de sécurité Active Directory spécifié. Un administrateur ou membre du groupe Active Directory délégué disposant des autorisations appropriées pour ajouter des utilisateurs à un groupe de sécurité (par exemple, administrateur, opérateurs de compte) doit ajouter un objet utilisateur au groupe de sécurité ou au groupe de la liste de contrôle pour l’utilisateur. Utilisez les fonctions indiquées. **(2)** uniquement pour les flux de travail attribués par le CsResponseGroupAdministrator à CsResponseGroupManager. **(3)** un responsable de groupe de réponse peut affecter un autre membre de CsResponseGroupManager à un flux de travail géré par le responsable actuel. **(4)** CsViewOnlyAdministrator ne peut exécuter que des applets de action de verbe «Get».

## <a name="response-group-configuration-prerequisites"></a>Conditions préalables à la configuration de Response Group

Response Group nécessite les composants suivants:

- service d’application

- application Response Group

- Modules linguistiques

- Magasin de fichiers (pour conserver les fichiers audio)

- Services Web (comprend les outils de configuration de Response Group et la console de connexion et de connexion des agents)

Tous ces composants sont installés par défaut lorsque vous déployez Enterprise Voice.

Vous devrez peut-être effectuer les tâches suivantes avant de configurer Response Group:

- Activez les utilisateurs pour Lync Server 2013 et voix entreprise.

- Modification d’un fichier de configuration pour la conformité aux normes FIPS (Federal Information Processing Standard)

- Modification du classement de base de données pour prendre en charge les caractères Yi, Meng et Zang pour les noms des files d’attente et des groupes d’agents

### <a name="enabling-users"></a>Activation des utilisateurs

La première étape de la configuration d’un groupe de réponse consiste à créer des groupes d’agents. Avant de créer un groupe d’agents, vous devez activer les utilisateurs qui seront agents de Response Group pour Skype entreprise et voix entreprise. L’activation des utilisateurs pour Skype entreprise est généralement une étape du déploiement d’Enterprise Edition Server ou Standard Edition Server. Pour plus d’informations sur l’activation des utilisateurs pour Skype entreprise, voir [activer ou désactiver des utilisateurs pour Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx). L’activation des utilisateurs pour voix entreprise est généralement une étape du déploiement voix entreprise. Pour plus d’informations, reportez-vous à la rubrique [activer les utilisateurs pour voix entreprise dans Skype entreprise Server](enable-users-for-enterprise-voice.md).

### <a name="complying-with-fips-requirements"></a>Conformité aux normes FIPS

Cette section ne vous concerne que si votre organisation doit se conformer aux normes FIPS (Federal Information Processing Standard).

Pour respecter les normes FIPS, vous devez modifier le fichier d’application Web.config afin d’utiliser un autre algorithme de chiffrement une fois les services web installés. Vous devez préciser qu’ASP.NET utilise l’algorithme de chiffrement triple 3DES (Triple Data Encryption Standard) pour traiter les données d’état d’affichage. Dans le cas d’une application de groupe de réponse, cette exigence s’applique à l’outil de configuration de Response Group et à la console de connexion et de connexion de l’agent. Pour plus d’informations sur cette configuration requise, voir l’article de la base de connaissances Microsoft 911722, «vous pouvez recevoir un message d’erreur lorsque vous accédez à des pages Web ASP.NET dont ViewState est activé après la mise [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkId=196183)à niveau de ASP.net 1,1 vers ASP.NET 2,0» à l’adresse.

Pour modifier le fichier Web.config, procédez comme suit :

1. Dans un éditeur de texte, comme Bloc-Notes, ouvrez le fichier d’application Web.config.

2. Dans le fichier Web. config, recherchez la `<system.web>` section.

3. Ajoutez la section `<machineKey>` suivante dans la `<system.web>` section:

   ```
   <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>
   ```

4. Enregistrez le fichier Web.config.

5. Redémarrez le service Internet Information Services (IIS) en exécutant la commande suivante à l’invite de commandes:

   ```
   iisreset
   ```

### <a name="supporting-yi-meng-and-zang-characters"></a>Prise en charge des caractères Yi, Meng et Zang

Cette section ne vous concerne que si votre organisation doit prendre en charge les caractères Yi, Meng ou Zang.

> [!NOTE]
> Pour plus d’informations sur les caractères Yi, Meng et Zang et pourquoi ils peuvent être importants pour votre déploiement, voir les informations sur les jeux [https://go.microsoft.com/fwlink/p/?linkId=240223](https://go.microsoft.com/fwlink/p/?linkId=240223)de caractères GB18030.

Pour assurer une prise en charge des caractères Yi, Meng ou Zang, vous devez modifier le classement de la base de données Rgsconfig. Modifiez le classement de la colonne **Nom** des tableaux ci-dessous dans chaque base de données Rgsconfig :

- dbo.AgentGroups

- dbo.BusinessHours

- dbo.HolidaySets

- dbo.Queues

- dbo.Workflows

Pour SQL Server 2008 R2 et SQL Server 2012, utilisez le classement Latin_General_100 (accent sensible). Si vous utilisez ce classement, certains noms d’objet ne dépendent pas des minuscules/majuscules.

Vous pouvez modifier le classement à l’aide de Microsoft SQL Server Management Studio. Pour plus d’informations sur l’utilisation de cet outil, voir la section [«utilisation de SQL Server Management Studio»](https://go.microsoft.com/fwlink/p/?linkId=196184). Pour modifier le classement, procédez comme suit :

1. Assurez-vous que SQL Server Management Studio est configuré de manière à autoriser les modifications nécessaires à la recréation des tables. Pour plus d’informations, reportez-vous à [la boîte de dialogue «Enregistrer (non autorisé)»](https://go.microsoft.com/fwlink/p/?linkId=196186). Pour plus d’informations sur la définition d’un assemblage de colonnes, voir [la section «Procédure: définir l’assemblage de colonnes (Visual Database Tools)»](https://go.microsoft.com/fwlink/p/?linkId=196185).

2. À l’aide de Microsoft SQL Server Management Studio, connectez-vous à la base de données Rgsconfig.

3. Recherchez la table à modifier dans la base de données Rgsconfig, cliquez avec le bouton droit sur la table, puis cliquez sur **Conception**.

4. Modifiez le classement de la colonne **Nom** et enregistrez la table.

## <a name="response-group-deployment-steps"></a>Procédure de déploiement de Response Group

**Procédure de déploiement du groupe Response Group**

|**Phase**|**Étapes**|**Autorisations**|**Documentation de déploiement**|
|:-----|:-----|:-----|:-----|
|Permettre aux utilisateurs de Skype entreprise et voix entreprise  <br/> |Autorisez les utilisateurs qui seront agents de Skype entreprise et voix entreprise. Les utilisateurs doivent être activés pour pouvoir être ajoutés aux groupes d’agents. En général, les utilisateurs sont activés pour Skype entreprise lors du déploiement du serveur Enterprise Edition ou Standard Edition Server. Les utilisateurs sont activés pour voix entreprise pendant le déploiement de voix entreprise.  <br/> |RTCUniversalUserAdmins  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Enable or Disable Users for Lync Server 2013 Preview](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx) <br/> [Activer les utilisateurs pour voix entreprise dans Skype entreprise Server](enable-users-for-enterprise-voice.md) <br/> |
|Créer et configurer les groupes Response Group, qui sont composés de groupes d’agents, de files d’attente et de flux de travail  <br/> |1. Utilisez le panneau de configuration Skype entreprise Server ou Skype entreprise Server Management Shell pour effectuer les opérations suivantes:  <br/> a. Créez et configurez des groupes d’agents.  <br/> b. Créez et configurez des files d’attente.  <br/> 2. Si vous le souhaitez, vous pouvez utiliser Skype entreprise Server Management Shell pour créer des heures et des jours fériés prédéfinis.  <br/> 3. à l’aide de l’outil de configuration de Response Group ou de Skype entreprise Server Management Shell, vous pouvez créer des flux de travail (groupes de recherche ou flux d’appels de réponse vocale interactifs), y compris des heures et des jours fériés personnalisés.  <br/> Vous pouvez accéder à l’outil de configuration de Response Group par le biais du panneau de configuration Skype entreprise Server.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsResponseGroupManager  <br/> |[Create Response Group Agent Groups](https://technet.microsoft.com/library/2a80de17-ead0-46e8-8a27-7a4e233dbde0.aspx) <br/> [Create Response Group Queues](https://technet.microsoft.com/library/49cb86c7-2cfd-4a53-8408-d407475174ed.aspx) <br/> [Facultatif Définir des heures d’activité de groupe de réponse dans Skype entreprise](optional-define-response-group-business-hours.md) <br/> [Facultatif Définir des jeux de vacances de groupe de réponse dans Skype entreprise](optional-define-response-group-holiday-sets.md) <br/> [Conception et création de flux de travail de groupe de réponse dans Skype entreprise](designing-and-creating-response-group-workflows.md) <br/> |
|(Facultatif) Personnaliser les paramètres au niveau de l’application  <br/> |Utilisez Skype entreprise Server Management Shell pour personnaliser la configuration par défaut de l’utilisation de la musique, le fichier audio de musique par défaut, la période de grâce aux retours de l’agent et la configuration du contexte d’appel.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Gestion des paramètres du groupe de réponse au niveau de l’application dans Skype entreprise](managing-application-level-response-group-settings.md) <br/> |
|(Facultatif) Déléguer la gestion des groupes Response Group  <br/> |Affectez aux utilisateurs le rôle CsResponseGroupManager pour déléguer la configuration de Response groups. Les responsables de groupe de réponse peuvent alors configurer les groupes de réponse qui leur sont attribués.  <br/> |RTCUniversalServerAdmins  <br/> CsResponseGroupAdministrator  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Planning for Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) <br/> |
|Vérifier votre déploiement Response Group  <br/> |Testez la réponse aux appels des flux de travail de votre groupe de recherche et de votre système de réponse vocale interactive pour vérifier que la configuration fonctionne comme prévu.  <br/> |-  <br/> |-  <br/> |

## <a name="overview-of-workflow-creation-scenarios"></a>Vue d’ensemble des scénarios de création de flux de travail

Lorsque vous créez des flux de travail, deux scénarios sont possibles :

- **L’Administrateur crée et configure le flux de travail** : le membre du rôle CsResponseGroupAdministrator (ou équivalent) crée et active le flux de travail, ainsi que tous les éléments qu’il contient, comme les groupes d’agents, les files d’attente, les congés et les heures ouvrées, la musique d’attente, etc.

- **L’administrateur crée le flux de travail et le responsable configure les options** : le membre du rôle CsResponseGroupAdministrator (ou équivalent) définit l’URI SIP (Session Initiation Protocol) principal et le nom complet, affecte des membres du rôle CsResponseGroupManager, sélectionne une file d’attente et active le flux de travail. Le membre du rôle CsResponseGroupManager peut ensuite ouvrir une session et modifier la configuration du flux de travail en créant des groupes d’agents. Il affecte également le groupe à la file d’attente, configure le numéro de téléphone, les congés et les heures ouvrées, la musique d’attente, etc.

    > [!NOTE]
    > Lorsque vous voulez créer un flux de travail géré, vous devez créer le flux travail en tant que flux de travail actif. Une fois que vous avez enregistré un flux de travail géré et actif, vous pouvez le modifier et le désactiver.


