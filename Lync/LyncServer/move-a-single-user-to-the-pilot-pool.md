---
title: Déplacement d’un utilisateur vers le pool pilote
TOCTitle: Déplacement d’un utilisateur vers le pool pilote
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205401(v=OCS.15)
ms:contentKeyID: 49299244
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déplacement d’un utilisateur vers le pool pilote

 

_**Dernière rubrique modifiée :** 2012-09-26_

Vous pouvez déplacer un utilisateur de votre pool Lync Server 2010 vers votre premier pool Lync Server 2013 à l’aide du Panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell. Dans l’exemple ci-dessous, dans la colonne pool de serveurs d’inscriptions, **pool01.contoso.net** est le pool Lync Server 2010, auquel les six utilisateurs sont tous connectés. Utilisez les procédures suivantes pour déplacer un utilisateur vers votre pool Lync Server 2013 à l’aide du Panneau de configuration Lync Server 2013 et de Lync Server Management Shell.

## Déplacer un utilisateur à l’aide de Panneau de configuration Lync Server 2013

**Liste des utilisateurs dans le Panneau de configuration Lync Server 2013**

![Boîte de dialogue Panneau de configuration Lync Server, déplacement d’utilisateurs](images/JJ205401.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Boîte de dialogue Panneau de configuration Lync Server, déplacement d’utilisateurs")

1.  Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou associé au rôle d’admistrateur CsAdministrator ou CsUserAdministrator.

2.  Ouvrez le **Paneau de configuration Lync Server**.

3.  Cliquez successivement sur **Utilisateurs**, Rechercher, puis sur **Trouver**.

4.  Sélectionnez un utilisateur à déplacer vers le pool Lync Server 2013. Dans l’exemple suivant, nous déplacerons l’utilisateur Sara Davis.

5.  Dans le menu **Action**, sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool**.

6.  Dans la liste déroulante, sélectionnez le pool Lync Server 2013.

7.  Cliquez sur **Action**, puis sur **Déplacer les utilisateurs sélectionnés vers le pool**. Cliquez sur **OK**.
    
    ![Boîte de dialogue Déplacement d’utilisateurs, pool du registre de destination](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Boîte de dialogue Déplacement d’utilisateurs, pool du registre de destination")  

8.  Vérifiez que la colonne **Pool de serveurs d’inscriptions** pour l’utilisateur contient désormais le pool Lync Server 2013. Cela signifie que l’utilisateur a été déplacé avec succès.

## Pour déplacer un utilisateur à l’aide de Lync Server 2013 Management Shell

1.  Ouvrez Lync Server Management Shell.

2.  Dans la ligne de commande, tapez ce qui suit :
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  Ensuite, dans la ligne de commande, tapez ce qui suit :
    
        Get-CsUser -Identity "David Pelton"

4.  L’identité **RegistrarPool** pointe désormais vers le pool Lync Server 2013. La présence de cette identité confirme que l’utilisateur a bien été déplacé.
    
    ![Sortie de l’applet de commande Get-CsUser avec filtre Identité](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Sortie de l’applet de commande Get-CsUser avec filtre Identité")  
    
    > [!NOTE]  
    > Pour plus d’informations sur l’applet de commande <strong>Get-CsUser</strong> , exécutez  : <strong>Get-Help Get-CsUser–Detailed</strong>
