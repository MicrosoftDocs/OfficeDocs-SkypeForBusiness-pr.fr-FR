---
title: Déplacer les données du magasin de fichiers vers un nouveau magasin de fichiers Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Si vous devez supprimer le serveur de fichiers qui joue actuellement le rôle de magasin de fichiers pour votre déploiement Skype Entreprise Server 2015, ou si vous devez apporter d’autres modifications qui rendraient le magasin de fichiers actuel indisponible, vous devez d’abord créer un nouveau partage. Ensuite, vous devez effectuer les étapes suivantes :'
ms.openlocfilehash: 73e66930f4c47ead3df01e04d30930b0257204e2
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778374"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a>Déplacer les données du magasin de fichiers vers un nouveau magasin de fichiers Skype Entreprise Server 2015

Si vous devez supprimer le serveur de fichiers qui joue actuellement le rôle de magasin de fichiers pour votre déploiement Skype Entreprise Server 2015, ou si vous devez apporter d’autres modifications qui rendraient le magasin de fichiers actuel indisponible, vous devez d’abord créer un nouveau partage. Ensuite, vous devez effectuer les étapes suivantes :

1. Fermez les Skype Entreprise Server 2015 qui utilisent le magasin de fichiers que vous prévoyez de supprimer.

2. Définissez le magasin de fichiers dans le Générateur de topologie et publiez les modifications pour rendre le nouveau magasin de fichiers disponible pour votre déploiement.

3. Déplacez les données vers le nouveau magasin de fichiers.

4. Redémarrez les serveurs ou les services.

5. Éventuellement, supprimez l’ancien partage de fichiers et le dossier de fichiers.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>Pour déplacer les données du magasin de fichiers vers le nouveau magasin

1. Connectez-vous à un ordinateur en tant que membre du groupe RTCUniversersalServerAdmins ou CsServerAdministrator sur lequel les outils d’administration Skype Entreprise Server 2015 sont installés.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.

4. Pour chaque pool directeur, directeur, serveur Édition Standard et pool frontal qui utilise le magasin de fichiers que vous prévoyez de supprimer, sélectionnez le serveur ou le pool, cliquez sur **Action,** puis cliquez sur Arrêter tous les **services.**

5. Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.

6. Démarrez le Générateur de topologie : cliquez sur Démarrer, sur Tous les **programmes,** sur **Skype Entreprise Server 2015,** puis sur Skype Entreprise Server **2015Topology Builder**.

7. Sélectionnez un serveur ou un pool qui utilise le magasin de fichiers et faites les choses suivantes :

8. Cliquez avec le bouton droit sur le serveur ou le pool, puis cliquez **sur Modifier les propriétés.**

9. Dans **Modifier les propriétés,** sous **Associations,** sous **Magasin de fichiers,** cliquez sur **Nouveau**.

10. Dans **Définir un nouveau magasin de** fichiers, sous **FQDN** du serveur de fichiers, tapez le nom de domaine complet (FQDN) du serveur de fichiers. Sous **Partage de fichiers,** tapez le nom du dossier du nouveau partage de fichiers, puis cliquez sur **OK.**

     > [!IMPORTANT]
     > Cette étape définit un nouveau magasin de fichiers à utiliser dans le Générateur de topologies. Vous ne la définissez qu’une seule fois, et non pour chaque serveur. Avant de publier la topologie, vous devez créer le partage de fichiers défini sur le serveur de fichiers défini. Pour plus d’informations, voir [Define the File Store for the Front End](/previous-versions/office/communications/gg133895(v=ocs.14)).

11. Pour chaque serveur ou pool qui utilise le magasin de fichiers, faites les choses suivantes :

12. Cliquez avec le bouton droit sur le serveur ou le pool, puis cliquez sur **Modifier les propriétés.**

13. Dans **Modifier les propriétés,** sous **Associations,** **dans** le magasin de fichiers, sélectionnez le nouveau partage de fichiers, puis cliquez sur **OK**.

14. Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Skype Entreprise Server déploiement si nécessaire. Pour plus d’informations, voir [Common Procedures for Removing Lync Servers and Components](/previous-versions/office/skype-server-2010/gg195688(v=ocs.14)).

15. Démarrez une invite de commandes : cliquez **sur Démarrer,** sur **Exécuter,** puis tapez cmd.exe.

16. Dans la ligne de commande, tapez le code suivant :

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > Le commutateur /S copie les fichiers, répertoires et sous-répertoires. Le commutateur /XF ignore tous les fichiers nommés Meeting.Active. Les versions actuelles de robocopy.exe avec le commutateur /MT offrent une vitesse de copie bien plus élevée en ayant recours à plusieurs threads. Pour le commutateur /LOG, utilisez un chemin d’accès au répertoire et un nom de fichier journal sous la forme C:\Logfiles\log.txt. Ce commutateur crée un fichier journal d’opérations à l’emplacement nommé.

17. Lorsque la copie des données est terminée, dans le Panneau de contrôle Lync Server, cliquez sur **Topologie,** puis sur **État**.

18. Pour chaque serveur ou pool sur lequel vous avez arrêté les services, sélectionnez le serveur ou le pool, cliquez sur **Action,** puis cliquez sur **Démarrer tous les services.**

19. Supprimez l’ancien magasin de fichiers de la topologie, puis publiez la topologie. Pour plus d’informations, voir [Remove a file store](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14)).

20. (Facultatif) Ouvrez une session sur l’ordinateur qui contient le magasin de fichiers que vous venez de supprimer en tant que membre du groupe Administrateurs local ou du groupe Administrateurs de domaine, puis supprimez l’ancien répertoire et l’ancien partage de fichiers.

## <a name="see-also"></a>Voir aussi

[Réattribuer un serveur à un magasin de fichiers différent](/previous-versions/office/skype-server-2010/gg195633(v=ocs.14))

[Supprimer un magasin de fichiers](/previous-versions/office/skype-server-2010/gg195635(v=ocs.14))