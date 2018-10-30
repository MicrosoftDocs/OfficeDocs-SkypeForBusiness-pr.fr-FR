---
title: Déplacement de plusieurs utilisateurs vers le pool pilote
TOCTitle: Déplacement de plusieurs utilisateurs vers le pool pilote
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205096(v=OCS.15)
ms:contentKeyID: 49298080
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déplacement de plusieurs utilisateurs vers le pool pilote

 

_**Dernière rubrique modifiée :** 2012-10-02_

Vous pouvez déplacer plusieurs utilisateurs de votre pool Lync Server 2010 vers votre premier pool Lync Server 2013 à l’aide du Panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.

## Pour déplacer plusieurs utilisateurs à l’aide de Panneau de configuration Lync Server 2013

1.  Ouvrez le **Panneau de configuration Lync Server** .

2.  Cliquez sur **Utilisateurs** , sur Rechercher, puis sur **Rechercher** .

3.  Sélectionnez deux utilisateurs que vous voulez déplacer vers le pool Lync Server 2013. Dans cet exemple, nous allons déplacer les utilisateurs Chen Yang et Claus Hansen.
    
    ![Déplacement d’utilisateurs vers un pool du registre spécifique](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Déplacement d’utilisateurs vers un pool du registre spécifique")  

4.  Dans le menu **Action** , sélectionnez **Déplacer les utilisateurs sélectionnés vers le pool** .

5.  Dans la liste déroulante, sélectionnez le pool Lync Server 2013.

6.  Cliquez sur **Action** , puis sur **Déplacer les utilisateurs sélectionnés vers le pool** . Cliquez sur OK.
    
    ![Boîte de dialogue Déplacement d’utilisateurs, pool du registre de destination](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Boîte de dialogue Déplacement d’utilisateurs, pool du registre de destination")  

7.  Vérifiez que la colonne **Pool de serveurs d’inscriptions** des utilisateurs contient maintenant le pool Lync Server 2013, ce qui indique que les utilisateurs ont été déplacés avec succès.

## Pour déplacer plusieurs utilisateurs à l’aide de Lync Server 2013 Management Shell

1.  Ouvrez Lync Server 2013 Management Shell.

2.  Dans la ligne de commande, tapez ce qui suit en remplaçant **User1** et **User2** par les noms des utilisateurs spécifiques que vous voulez déplacer et **pool\_FQDN** par le nom du pool de destination. Dans cet exemple, nous allons déplacer les utilisateurs Hao Chen et Katie Jordan.
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    ![Exemple d’applet de commande PowerShell Get-CsUser](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Exemple d’applet de commande PowerShell Get-CsUser")  

3.  Dans la ligne de commande, tapez ce qui suit :
    
        Get-CsUser -Identity "User1"

4.  L’identité **Registrar Pool** doit désormais pointer vers le pool que vous avez spécifié en tant que **pool\_FQDN** à l’étape précédente. La présence de cette identité confirme que l’utilisateur a été déplacé avec succès. Répétez cette étape pour vérifier que **User2** a été déplacé.
    
    ![Sortie de l’applet de commande PowerShell Get-UsUser -Identity](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Sortie de l’applet de commande PowerShell Get-UsUser -Identity")  

## Pour déplacer simultanément tous les utilisateurs à l’aide de Lync Server 2013 Management Shell

Dans cet exemple, tous les utilisateurs ont été replacés dans le pool Lync Server 2010 (pool01.contoso.net). À l’aide de Lync Server 2013 Management Shell, nous allons déplacer simultanément tous les utilisateurs vers le pool Lync Server 2013 (pool02.contoso.net).

1.  Ouvrez le **Lync Server 2013 Management Shell**.

2.  Dans la ligne de commande, tapez ce qui suit :
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    ![Applets de commande PowerShell et résultats dans Management Shell](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "Applets de commande PowerShell et résultats dans Management Shell")  

3.  Exécutez ensuite **Get-CsUser** pour l’un des utilisateurs pilotes.
    
        Get-CsUser -Identity "Hao Chen"

4.  L’identité **Registrar Pool** de chaque utilisateur pointe maintenant vers le pool que vous avez spécifié comme « pool\_FQDN » à l’étape précédente. La présence de cette identité confirme que l’utilisateur a été déplacé avec succès.

5.  Par ailleurs, nous pouvons afficher la liste des utilisateurs dans le Panneau de configuration Lync Server 2013 et vérifier que la valeur Registrar Pool pointe désormais vers le pool Lync Server 2013.
    
    ![Liste des utilisateurs du Panneau de configuration Lync Server 2013](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Liste des utilisateurs du Panneau de configuration Lync Server 2013")

