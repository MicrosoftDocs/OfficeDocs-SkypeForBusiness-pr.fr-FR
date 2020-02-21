---
title: 'Lync Server 2013 : création ou modification d’une stratégie de conférence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing policy
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49733844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 522f1d1240e73775ae1f0976556b882ba00fe1d3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-policy-in-lync-server-2013"></a>Création ou modification d’une stratégie de conférence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-07_

Effectuez les étapes suivantes pour créer une stratégie de conférence au niveau de l’utilisateur ou au niveau du site. Pour plus d’informations sur l’affectation d’une stratégie de niveau utilisateur à un utilisateur, voir [assigner une stratégie de conférence par utilisateur dans Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md). Pour obtenir la liste de tous les paramètres de stratégie de conférence disponibles, consultez la rubrique [référence des paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>

## <a name="to-create-a-new-user-or-site-policy"></a>Pour créer une nouvelle stratégie utilisateur ou de site

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.

4.  Cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :
    
      - Pour créer une stratégie au niveau de l’utilisateur, cliquez sur **Stratégie utilisateur**. Dans **Nouvelle stratégie de conférence**, dans **Nom**, tapez un nom descriptif pour la stratégie.
    
      - Pour créer une stratégie au niveau site, cliquez sur **Stratégie de site**. Dans la zone de recherche **Sélectionner un site**, tapez entièrement ou partiellement le nom du site pour lequel vous voulez créer une stratégie. Dans la liste des sites, cliquez sur le site voulu, puis sur **OK**.
        
        <div>
        

        > [!NOTE]  
        > Le nom du site devient le nom de la stratégie de conférence et ne peut pas être modifié.

        
        </div>

5.  Dans **Description**, tapez la description de la stratégie.

6.  Sous **Stratégie de l’organisateur**, dans **Taille maximale de la réunion**, tapez le nombre maximal d’utilisateurs autorisés à participer à une réunion. Par défaut, la taille maximale de la réunion est définie sur 250.

7.  Pour empêcher les utilisateurs d’inviter des utilisateurs anonymes aux réunions, désactivez la case à cocher **Autoriser les participants à inviter des utilisateurs anonymes**. Les utilisateurs anonymes sont des utilisateurs qui n’ont pas d’informations d’identification dans les services de domaine Active Directory de votre organisation et qui, par conséquent, ne sont pas authentifiés. Par défaut, les utilisateurs peuvent inviter des utilisateurs anonymes aux réunions.

8.  Dans **Enregistrement**, effectuez l’une des opérations suivantes :
    
      - Pour interdire aux participants d’enregistrer les réunions, cliquez sur **Aucun**. Il s’agit du paramètre par défaut.
    
      - Pour autoriser les participants à enregistrer les réunions, cliquez sur **Activer l’enregistrement**.

9.  Pour autoriser les participants externes à enregistrer les réunions, activez la case à cocher **Autoriser les participants fédérés et anonymes à enregistrer**. Par défaut, le système interdit aux participants externes d’enregistrer les réunions.

10. Dans **Audio/vidéo**, effectuez l’une des opérations suivantes :
    
      - Pour interdire l’utilisation de l’audio et de la vidéo, cliquez sur **Aucun**.
    
      - Pour autoriser l’utilisation de l’audio mais pas de la vidéo, cliquez sur **Activer Audio sur IP**.
    
      - Pour autoriser l’utilisation de l’audio et de la vidéo, cliquez sur **Activer l’audio/la vidéo IP**. Il s’agit du paramètre par défaut.

11. Si vous avez choisi d’autoriser l’utilisation de l’audio dans **Audio/vidéo**, procédez comme suit :
    
      - Pour empêcher les utilisateurs de rejoindre la réunion via un appel à distance, désactivez la case à cocher **Activer la conférence rendez-vous PSTN**. Par défaut, les utilisateurs peuvent accéder aux réunions par le biais du réseau téléphonique commuté (RTC).
    
      - Si vous autorisez les utilisateurs à accéder aux réunions à distance et que vous souhaitez autoriser les utilisateurs non authentifiés (anonymes) à rejoindre une réunion via un appel téléphonique sortant, activez la case à cocher **Autoriser l’accès sortant des participants anonymes**. Avec l’appel téléphonique sortant, le serveur de conférence appelle l’utilisateur et celui-ci répond au téléphone pour rejoindre la réunion. Par défaut, les utilisateurs anonymes ne peuvent pas rejoindre une réunion via un appel téléphonique sortant.

12. Si vous décidez d’autoriser l’utilisation de la vidéo dans **Audio/vidéo**, cochez **Autoriser plusieurs flux vidéo** .

13. Dans **Collaboration de données**, effectuez l’une des opérations suivantes :
    
      - Pour empêcher la collaboration de données, cliquez sur **Aucun**.
    
      - Pour autoriser la collaboration de données, cliquez sur **Activer la collaboration de données**. Il s’agit du paramètre par défaut.

14. Si vous avez choisi d’autoriser la collaboration de données dans **Collaboration de données**, procédez comme suit :
    
      - Pour interdire les téléchargements externes, désactivez la case à cocher **Autoriser les participants fédérés et anonymes à télécharger du contenu**. Par défaut, les utilisateurs externes peuvent télécharger du contenu.
    
      - Pour interdire les transferts de fichiers, désactivez la case à cocher **Autoriser les participants à transférer des fichiers**. Par défaut, les utilisateurs peuvent transférer des fichiers.
    
      - Pour interdire l’utilisation des annotations, désactivez la case à cocher **Activer les annotations**. Pour autoriser l’utilisation des annotations dans les présentations PowerPoint, désactivez la case à cocher **Activer les annotations PowerPoint**. Par défaut, les annotations sont autorisées.
    
      - Pour interdire l’utilisation des sondages, désactivez la case à cocher **Activer les sondages**. Par défaut, les sondages sont autorisés.

15. Dans **Partage d’application**, effectuez l’une des opérations suivantes :
    
      - Pour interdire l’utilisation du partage d’application, cliquez sur **Désactiver le partage d’application**.
    
      - Pour autoriser l’utilisation du partage d’application, cliquez sur **Activer le partage d’application**. Il s’agit du paramètre par défaut.

16. Si vous avez choisi d’autoriser le partage d’application dans **Partage d’application**, procédez comme suit :
    
      - Pour empêcher les participants à la réunion de prendre le contrôle du partage d’application, désactivez la case à cocher **Autoriser les participants à prendre le contrôle**. Par défaut, les participants peuvent prendre le contrôle du partage d’application.
    
      - Si vous avez choisi d’autoriser les participants à la réunion à prendre le contrôle du partage d’application, activez la case à cocher **Autoriser les participants fédérés et anonymes à prendre le contrôle** pour autoriser les utilisateurs externes à prendre le contrôle du partage d’application. Par défaut, les utilisateurs externes ne peuvent pas prendre le contrôle du partage d’application.

17. Sous **Stratégie du participant**, effectuez l’une des opérations suivantes :
    
      - Pour interdire le partage d’application et le partage du Bureau, cliquez sur **Désactiver le partage d’application et de Bureau**.
    
      - Pour autoriser le partage d’application mais pas le partage du Bureau, cliquez sur **Activer le partage d’application**.
    
      - Pour autoriser le partage d’application et le partage du Bureau, cliquez sur **Activer le partage d’application et de Bureau**. Il s’agit du paramètre par défaut.

18. Pour interdire les transferts de fichiers d’homologue à homologue, désactivez la case à cocher **Autoriser le transfert de fichiers entre homologues**. Par défaut, les transferts de fichiers d’homologue à homologue sont autorisés.

19. Pour autoriser l’enregistrement d’homologue à homologue, activez la case à cocher **Activer l’enregistrement entre homologues**. Par défaut, l’enregistrement d’homologue à homologue n’est pas autorisé.

20. Pour autoriser les participants à participer avec plusieurs flux vidéo, activez la case à cocher **Autoriser les participants à participer avec plusieurs flux vidéo**. Par défaut, les flux vidéo multiples sont autorisés.

21. Cliquez sur **Valider**.

</div>

<div>

## <a name="to-modify-an-existing-user-or-site-policy"></a>Pour modifier une stratégie utilisateur ou de site existante

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Stratégie de conférence**.

4.  Dans la liste des stratégies de conférence, cliquez sur la stratégie de conférence souhaitée, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la stratégie de conférence**, modifiez les paramètres de stratégie, à l’exception du nom de la stratégie qui ne peut pas être modifié.

6.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

