---
title: "Lync Server 2013 : Util. de la connectivité Lync-Skype en tant qu’util. final"
TOCTitle: Utilisation de la connectivité Lync-Skype en tant qu’utilisateur final
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn440175(v=OCS.15)
ms:contentKeyID: 59602878
ms.date: 12/28/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation de la connectivité Lync-Skype dans Lync Server 2013 en tant qu’utilisateur final

 

_**Dernière rubrique modifiée :** 2016-12-27_

La connectivité Lync-Skype permet aux utilisateurs Skype et Lync de s’ajouter mutuellement comme contacts, d’échanger des messages instantanés et de passer des appels audio et vidéo. Lorsqu’un utilisateur Skype ajoute un utilisateur Lync il crée un contact dans Skype contenant l’URI (Uniform Resource Identifier) du protocole SIP (Session Initiation Protocol) de l’utilisateur Lync. À l’inverse, lorsqu’un utilisateur Lync ajoute un contact Skype, il crée un contact dans Lync user will create a contact in Lync qui contiendra le compte Microsoft de l’utilisateur Skype, et non le nom d’utilisateur Skype..

**Qu’est-ce qu’un compte Microsoft ?** Les utilisateurs Skype doivent se connecter à Skype à l’aide d’un compte Microsoft (précédemment appelé Windows Live ID) pour communiquer avec des contacts Lync. Un compte Microsoft est constitué d’une adresse de messagerie et d’un mot de passe, que vous pouvez également utiliser pour vous connecter à des services tels que la technologie de stockage Microsoft OneDrive Windows Phone, le service de jeux en ligne Microsoft Xbox LIVE et le client de messagerie et de collaboration Microsoft Outlook (et auparavant, le service de messagerie électronique Web Microsoft Hotmail ou Windows Live Messenger). Si vous utilisez une adresse de messagerie ou un mot de passe pour vous connecter à ces services ou à d’autres, vous avez déjà un compte Microsoft.Pour plus d’informations sur la création d’un compte Microsoft, reportez-vous à la page de connexion aux comptes Microsoft à l’adresse [http://go.microsoft.com/fwlink/p/?LinkId=306061](http://go.microsoft.com/fwlink/p/?linkid=306061). Vous pouvez fusionner votre compte Skype existant avec votre compte Microsoft pour une authentification unique sur plusieurs applications et services. Une fois la fusion effectuée, un utilisateur Skype peut envoyer une demande de contact à un utilisateur Lync.

> [!IMPORTANT]  
> Pour que les utilisateurs Lync et Skype puissent communiquer les uns avec les autres, les conditions suivantes doivent être remplies :<ul><li><p>Les utilisateurs Skype doivent être connectés à leur client Skype à l’aide d’un compte Microsoft.</p></li>
> <li><p>La connectivité PIC (Public IM Connectivity) doit être activée pour les utilisateurs Lync par leur administrateur Lync.</p></li>
> <li><p>Lorsqu’un utilisateur Skype ajoute un contact Lync, vérifiez que le mot Lync s’affiche sous le nom du contact. Cela indique qu’un URI Lync a été détecté.</p></li>
> <li><p>Si aucun résultat de recherche n’est renvoyé pour le domaine Lync lorsqu’un utilisateur Skype ajoute un contact Lync, il est possible que le processus d’approvisionnement des informations PIC ne soit pas terminé ou que le domaine Lync ne soit pas encore configuré.</p></li>
> <li><p>Selon les paramètres de confidentialité des utilisateurs Lync et Skype, il est possible que la messagerie instantanée, la vidéo et la présence ne fonctionnent pas tant que les nouveaux contacts ne sont pas acceptés par chaque utilisateur.</p></li></ul>


**Pour ajouter un contact Skype à Lync 2013**

1.  À partir de Lync, cliquez sur **Ajouter un contact, Ajouter un contact qui ne fait pas partie de ma société**.

2.  À partir de la liste des fournisseurs de contacts, sélectionnez **Skype**, comme indiqué ci-dessous.
    
    ![Client Lync montrant comment ajouter un contact Skype](images/Dn440175.ac4e2f21-c1d9-47d8-b99e-d49fe4eb36d7(OCS.15).jpg "Client Lync montrant comment ajouter un contact Skype")

3.  Dans le champ **Adresse de messagerie instantanée**, entrez le compte Microsoft de l’utilisateur Skype.

4.  Dans la liste déroulante **Ajouter au groupe de Contacts**, sélectionnez un groupe de contacts auquel ajouter l’utilisateur.

5.  Dans la liste déroulante **Définir le niveau de confidentialité**, sélectionnez le paramètre de contact approprié, puis cliquez sur **OK**.

6.  L’utilisateur s’affiche désormais comme contact dans Lync. Sélectionnez l’utilisateur, cliquez avec le bouton droit sur son nom, puis cliquez sur **Afficher la carte de visite** pour afficher les propriétés de l’utilisateur. Comme indiqué ci-dessous, vous pouvez également cliquer sur **Appeler**puis sur **Appel Lync** pour passer un appel audio ou vidéo avec l’utilisateur Skype tout juste ajouté.
    
    ![Client Lync démarrant un appel Lync avec un contact](images/Dn440175.cd7cb21a-87f7-4bfa-b30c-980d4098d226(OCS.15).jpg "Client Lync démarrant un appel Lync avec un contact")

Pour plus d’informations sur la prise en charge des contacts, reportez-vous à [Ajouter un contact dans Lync](http://office.microsoft.com/fr-fr/office365-lync-online-help/add-a-contact-in-lync-ha102828922.aspx) et [Ajouter un contact externe dans Lync](http://office.microsoft.com/fr-fr/office365-lync-online-help/add-an-external-contact-in-lync-ha104038998.aspx?ctt=5%26origin=ha102828922)

Lorsque le compte Microsoft d’un utilisateur Skype utilise un nom de domaine personnalisé tel que <strong>bob@contoso.com</strong>, un utilisateur Lync peut ajouter ce compte Microsoft à Lync de deux façons :

1.  en utilisant l’icône **Ajouter un contact**, ou

2.  en utilisant le champ **Rechercher une personne ou une salle, ou composer un numéro**.

Dans chaque instance, l’utilisateur Lync doit entrer l’adresse de messagerie de l’utilisateur Skype au format suivant : <strong>utilisateur(nom de domaine)@msn.com</strong>.

> [!IMPORTANT]  
> Cette étape n’est pas requise pour les comptes Microsoft qui utilisent les noms de domaine suivants : <strong>@live.com, @hotmail.com ou @outlook.com</strong>. Pour plus d’informations sur les noms de domaine personnalisés pris en charge, reportez-vous à <a href="http://support.microsoft.com/kb/897567">Supported public IM domains (Domaines de messagerie instantanée publique pris en charge)</a>.

**Pour ajouter un contact Skype à Lync lorsqu’un nom de domaine personnalisé est utilisé**

1.  À partir de Lync, cliquez sur **Ajouter un contact, Ajouter un contact qui ne fait pas partie de ma société**.

2.  À partir de la liste des fournisseurs de contacts, sélectionnez **Skype**, comme indiqué ci-dessous.
    
    ![Client Lync montrant comment ajouter un contact Skype](images/Dn440175.ac4e2f21-c1d9-47d8-b99e-d49fe4eb36d7(OCS.15).jpg "Client Lync montrant comment ajouter un contact Skype")

3.  Dans le champ **Adresse de messagerie instantanée**, entrez le compte Microsoft de l’utilisateur Skype au format <strong>utilisateur(nom de domaine)@msn.com</strong>. Par exemple, pour l’utilisateur bob@contoso.com, l’entrée serait <strong>bob(contoso.com)@msn.com</strong>, comme indiqué ci-dessous.
    
    ![Paramètres nouveaux contacts de client Lync](images/Dn440175.422e69b5-2c0c-4260-858f-f10309af772f(OCS.15).jpg "Paramètres nouveaux contacts de client Lync")

4.  Dans la liste déroulante **Ajouter au groupe de Contacts**, sélectionnez un groupe de contacts auquel ajouter l’utilisateur.

5.  Dans la liste déroulante **Définir le niveau de confidentialité**, sélectionnez le paramètre de contact approprié, puis cliquez sur **OK**.

6.  Un utilisateur Lync peut également utiliser le champ **Rechercher une personne ou une salle, ou composer un numéro** dans Lync, et ajouter une adresse semblable à la suivante : <strong>utilisateur(nom de domaine)@msn.com</strong>. Pour le compte Microsoft bob@contoso.com, l’entrée serait <strong>bob(contoso.com)@msn.com</strong>, comme indiqué ci-dessous.
    
    ![Recherche d’un contact dans un client Lync](images/Dn440175.69787db8-f9b9-49e5-b197-b90b10393301(OCS.15).jpg "Recherche d’un contact dans un client Lync")

7.  Suivez les étapes 4 et 5 plus haut dans cette procédure pour ajouter le contact à un groupe de contacts et sélectionner le niveau de confidentialité approprié.

**Pour ajouter un contact Lync à Skype**

1.  Connectez-vous à Skype. Les utilisateurs Skype doivent être connectés à leur client Skype à l’aide d’un compte Microsoft.
    
    ![Page de connexion de client Skype](images/Dn440175.b4fd7c5a-be35-4205-80c7-872863b7a91d(OCS.15).jpg "Page de connexion de client Skype")

2.  Sélectionnez l’icône Ajouter des contacts.

3.  Entrez l’URI SIP de l’utilisateur Lync (par exemple, bob@contoso.com).

4.  Lorsque Skype trouve une correspondance dans les résultats de recherche, recherchez le mot **Lync** sous le nom de l’utilisateur Lync. Celui-ci indique que Skype a correctement localisé l’URI SIP du client Lync. Cliquez sur le nom.
    
    ![Client Skype montrant un contact Lync](images/Dn440175.4e690a72-1a54-4442-89cf-0fb45ac5f56a(OCS.15).jpg "Client Skype montrant un contact Lync")

5.  Dans le coin supérieur droit de la fenêtre, cliquez sur Ajouter aux contacts.

6.  Le nouveau contact est ajouté à votre liste de contacts, mais un point d’interrogation s’affiche à la place de son icône de statut jusqu’à ce qu’il accepte votre demande. Une fois que votre nouveau contact accepte votre demande, vous pourrez voir s’il est en ligne, lancer des conversations par messagerie instantanée et passer des appels audio et vidéo.
    
    ![Conversation par messagerie instantanée de client Skype avec un contact Lync](images/Dn440175.86ca6f81-4db9-45ba-8511-1f7541aaf066(OCS.15).jpg "Conversation par messagerie instantanée de client Skype avec un contact Lync")
    
    > [!IMPORTANT]  
    > L’administrateur Lync Server doit configurer les paramètres de stratégie de l’utilisateur Lync pour autoriser les demandes entrantes, sans quoi l’utilisateur Lync ne recevra pas les demandes de contact de l’utilisateur Skype. Selon la configuration des paramètres de stratégie de l’utilisateur Skype, la demande d’ajout de l’utilisateur Skype s’affichera sous l’onglet <strong>Nouveau</strong> du client Lync. Pour commencer à communiquer avec l’utilisateur Skype, l’utilisateur Lync doit ajouter celui-ci à la liste des Favoris ou à une liste de contacts. L’image suivante montre l’emplacement de l’onglet <strong>Nouveau</strong> dans le client Lync.    
    ![Page Nouveaux contacts client Lync](images/Dn440175.b1cf8570-1401-47d9-ab14-b04f0d7e8a7a(OCS.15).jpg "Page Nouveaux contacts client Lync")

Un utilisateur Lync doit configurer les alertes Lync pour s’assurer que les demandes envoyées à partir d’un utilisateur Skype s’affichent et peuvent être détectées par l’utilisateur Lync. Pour configurer les alertes Lync, effectuez la procédure suivante.

**Pour configurer les alertes Lync**

1.  À partir du client Lync, cliquez sur l’icône **Options**.

2.  Sélectionnez **Alertes**.

3.  Sous **Alertes générales**, sélectionnez **M’avertir quand une personne m’ajoute à sa liste des contacts**.

4.  Sous **Contacts n’utilisant pas Lync**, sélectionnez **Autoriser les invitations, mais bloquer toutes les autres communications**.

5.  Cliquez sur **OK** pour fermer la fenêtre Options.

![Boîte de dialogue Options de client Lync, page Alertes](images/Dn440175.b36ed67f-f394-4f66-b60a-b74793001bfc(OCS.15).jpg "Boîte de dialogue Options de client Lync, page Alertes")

