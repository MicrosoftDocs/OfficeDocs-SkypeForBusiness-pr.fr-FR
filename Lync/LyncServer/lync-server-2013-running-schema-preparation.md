---
title: 'Lync Server 2013 : Exécution de la préparation du schéma'
TOCTitle: Exécution de la préparation du schéma
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412729(v=OCS.15)
ms:contentKeyID: 49298360
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exécution de la préparation du schéma Active Directory dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Vous pouvez utiliser le programme d’installation ou des applets de commande Lync Server Management Shell pour préparer le schéma Active Directory. L’applet de commande qui étend le schéma Active Directory est **Install-CsAdServerSchema**.

> [!NOTE]  
> L’applet de commande de préparaton de schéma (<strong>Install-CsAdServerSchema</strong>) doit accéder au contrôleur de schéma. Il est donc nécessaire que le service d’accès à distance au Registre soit en cours d’exécution et que la clé de Registre distante soit activée. Vous pouvez exécuter l’applet de commande localement sur le contrôleur de schéma si le service d’accès à distance au Registre ne peut pas y être activé. Pour plus d’informations sur l’accès à distance au Registre, reportez-vous à l’article 314837 « Comment gérer l’accès à distance au Registre » de la base de connaissances Microsoft, à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</a>.

Après avoir préparé le schéma, vérifiez manuellement que la partition du schéma a été répliquée avant de procéder à la préparation de la forêt. Pour plus d’informations, reportez-vous à [Vérification de la réplication de schéma Active Directory dans Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

## Pour utiliser le programme d’installation afin de préparer le schéma de la forêt actuelle

1.  Ouvrez une session sur un serveur de la forêt en tant que membre du groupe Administrateurs du schéma et avec les droits d’administrateur sur le maître de schémas.

2.  À partir du dossier ou du support d’installation de Lync Server 2013, exécutez le fichier Setup.exe pour démarrer l’Assistant Déploiement.

3.  Si vous êtes invité à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui** .

4.  La boîte de dialogue Installation de Lync Server 2013 vous invite à indiquer l’emplacement des fichiers Lync Server. Choisissez l’emplacement par défaut ou cliquez sur **Parcourir** pour accéder à un emplacement de votre choix, puis cliquez sur **Installer** .

5.  Dans la page Contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence** , puis cliquez sur **OK** .

6.  Le programme d’installation installe les composants principaux de Lync Server.

7.  Lorsque l’Assistant Déploiement est prêt, cliquez sur **Préparer Active Directory** et attendre le résultat quant à l’état du déploiement.

8.  À l’**Étape 1 : Préparer un schéma** , cliquez sur **Exécuter** .

9.  Dans la page **Préparer un schéma** , cliquez sur **Suivant** .

10. Dans la page **Exécution de commandes** , recherchez **Statut de la tâche : Terminée** , puis cliquez sur **Afficher le journal** .

11. Sous la colonne **Action** , développez **Préparation du schéma** , recherchez le résultat d’exécution **\<Opération réussie\>** à la fin de chaque tâche afin de vérifier que la préparation de schéma a abouti, fermez le journal, puis cliquez sur **Terminer** .

12. Attendez la fin de la réplication d’Active Directory ou forcez-la.

13. Vérifiez manuellement que les modifications de schéma ont été répliquées sur tous les autres contrôleurs de domaine. Pour plus d’informations, reportez-vous à [Vérification de la réplication de schéma Active Directory dans Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

## Pour utiliser des applets de commande afin de préparer le schéma de la forêt actuelle

1.  Ouvrez une session sur un ordinateur de la forêt en tant que membre du groupe Administrateurs du schéma disposant de droits d’administration sur le contrôleur de schéma.

2.  Installez les composants principaux de Lync Server en procédant comme suit :
    
    1.  À partir du dossier ou du support d’installation de Lync Server 2013, exécutez Setup.exe pour démarrer l’Assistant Déploiement de Lync Server.
    
    2.  Si vous êtes invité à installer le package redistribuable Microsoft Visual C++, cliquez sur **Oui** .
    
    3.  La boîte de dialogue Installation de Lync Server 2013 vous invite à indiquer l’emplacement des fichiers Lync Server. Choisissez l’emplacement par défaut ou cliquez sur **Parcourir** pour accéder à un emplacement de votre choix, puis cliquez sur **Installer** .
    
    4.  Dans la page Contrat de licence, activez la case à cocher **J’accepte les termes du contrat de licence** , puis cliquez sur **OK** . Le programme d’installation installe les composants principaux de Lync Server 2013.

3.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

4.  Exécutez :
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    Si vous omettez le paramètre Ldf, la valeur par défaut correspond au chemin d’installation de Lync Server 2013 lu à partir du Registre.
    
    Exemple :
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  Utilisez l’applet de commande suivante pour vérifier si la préparation de schéma a été exécutée avec succès.
    
        Get-CsAdServerSchema 
    
    Cette applet de commande renvoie la valeur **SCHEMA\_VERSION\_STATE\_CURRENT** si le schéma a été préparé correctement.

6.  Attendez la fin de la réplication d’Active Directory ou forcez-la.

7.  Vérifiez manuellement que les modifications de schéma ont été répliquées sur tous les autres contrôleurs de domaine. Pour plus d’informations, reportez-vous à [Vérification de la réplication de schéma Active Directory dans Lync Server 2013](lync-server-2013-verifying-schema-replication.md).

## Voir aussi

#### Tâches

[Vérification de la réplication de schéma Active Directory dans Lync Server 2013](lync-server-2013-verifying-schema-replication.md)  

#### Concepts

[Préparation du schéma Active Directory dans Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

