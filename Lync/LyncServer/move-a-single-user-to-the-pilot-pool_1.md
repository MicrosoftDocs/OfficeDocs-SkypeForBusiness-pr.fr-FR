---
title: Déplacement d’un utilisateur vers le pool pilote
TOCTitle: Déplacement d’un utilisateur vers le pool pilote
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49891414
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déplacement d’un utilisateur vers le pool pilote

 

_**Dernière rubrique modifiée :** 2012-09-28_

Vous pouvez déplacer un utilisateur de votre pool Office Communications Server 2007 R2 vers votre pool pilote Lync Server 2013 en utilisant le Panneau de configuration Lync Server 2013 ou Lync Server 2013 Management Shell. Dans l’exemple ci-dessous, dans la colonne Pool de serveurs d’inscriptions, **\<Office Communications Server\>** est le pool Office Communications Server 2007 R2, et les six utilisateurs sont connectés à ce pool. Utilisez les procédures suivantes pour déplacer un utilisateur vers votre pool Lync Server 2013 à l’aide du Panneau de configuration Lync Server 2013 et de Lync Server Management Shell.

![Rechercher des utilisateurs OCS dans le Panneau de configuration Lync Server](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Rechercher des utilisateurs OCS dans le Panneau de configuration Lync Server")

## Pour déplacer un utilisateur via le Panneau de configuration Lync Server 2013

1.  Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administrateur CsAdministrator ou CsUserAdministrator.

2.  Ouvrez le Panneau de configuration Lync Server.

3.  Cliquez sur **Utilisateurs**.

4.  Sous l’onglet **Recherche d’un utilisateur**, cliquez sur le bouton **Recherche**.

5.  Cliquez ensuite sur **Ajouter un filtre**.

6.  Créez un filtre où **Utilisateur Office Communications Server** a la valeur **True**.

7.  Cliquez sur **Recherche** pour rechercher les utilisateurs Office Communications Server 2007 R2 hérités.
    
    ![Rechercher des utilisateurs OCS dans le Panneau de configuration Lync Server](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Rechercher des utilisateurs OCS dans le Panneau de configuration Lync Server")  

8.  Sélectionnez un utilisateur que vous voulez déplacer vers le pool Lync Server 2013. Dans cet exemple, nous allons déplacer l’utilisateur Sara Davis.

9.  Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.

10. Dans la liste déroulante, sélectionnez le pool Lync Server 2013.

11. Cliquez sur **Action**, puis sur **Déplacer les utilisateurs sélectionnés vers le pool**. Cliquez sur **OK**.
    
    ![Définition du pool de destination dans la boîte de dialogue Déplacer des utilisateurs](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Définition du pool de destination dans la boîte de dialogue Déplacer des utilisateurs")  

12. Vérifiez que la colonne **Pool de serveurs d’inscriptions** de l’utilisateur contient maintenant le pool Lync Server 2013, ce qui indique que l’utilisateur a correctement été déplacé.

## Pour déplacer un utilisateur à l’aide de Lync Server 2013 Management Shell

1.  Ouvrez Lync Server Management Shell.

2.  Dans la ligne de commande, tapez ce qui suit :
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  Ensuite, dans la ligne de commande, tapez ce qui suit :
    
        Get-CsUser -Identity "David Pelton"

4.  L’identité **RegistrarPool** pointe désormais vers le pool Lync Server 2013. La présence de cette identité confirme que l’utilisateur a bien été déplacé.
    
    ![Sortie de l’applet de commande Get-CsUser avec filtre Identité](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Sortie de l’applet de commande Get-CsUser avec filtre Identité")  
    
    > [!NOTE]  
    > Pour plus d’informations sur l’applet de commande <strong>Get-CsUser</strong> , exécutez  : <strong>Get-Help Get-CsUser –Detailed</strong>
