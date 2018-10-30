---
title: Configuration de la passerelle XMPP sur Lync Server 2013
TOCTitle: Configuration de la passerelle XMPP sur Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49891210
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la passerelle XMPP sur Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-19_

Lorsque vous configurez des stratégies pour prendre en charge des partenaires fédérés XMPP (Extensible Messaging and Presence Protocol), les stratégies s’appliquent aux utilisateurs des domaines fédérés XMPP, mais pas aux utilisateurs des fournisseurs de services de messagerie instantanée SIP (Session Initiation Protocol), par exemple, Windows Live, ou de domaines SIP fédérés. Vous devez configurer un partenaire fédéré XMPP pour chaque domaine fédéré XMPP auquel vos utilisateurs pourront ajouter des contacts et avec lequel ils pourront communiquer. Une fois les stratégies en place, il ne vous reste plus qu’à configurer les certificats de la passerelle XMPP, déployer la passerelle XMPP de Lync Server 2013 et mettre à jour les enregistrements DNS pour la passerelle XMPP.

## Configurer des certificats pour la passerelle XMPP sur le serveur Edge Lync Server 2013

1.  Sur le serveur Edge, dans l’Assistant Déploiement, en regard de **Étape 3 : Demander, installer ou affecter les certificats** , cliquez sur **Réexécuter** .
    
    > [!TIP]  
    > Si vous déployez le serveur Edge pour la première fois, l’option Exécuter s’affiche au lieu de Réexécuter.

2.  Dans la page **Tâches se rapportant aux certificats disponibles** , cliquez sur **Créer une demande de certificat** .

3.  Dans la page **Demande de certificat** , cliquez sur **Certificat de serveur Edge externe** .

4.  Dans la page **Demande différée ou immédiate** , cochez la case **Préparer la demande maintenant, mais l’envoyer plus tard** .

5.  Dans la page **Fichier de demande de certificat** , tapez le chemin d’accès complet et le nom du fichier dans lequel la demande doit être enregistrée (par exemple, c:\\cert\_exernal\_edge.cer).

6.  Dans la page **Spécifier un autre modèle de certificat** , pour utiliser un autre modèle que le modèle WebServer par défaut, cochez la case **Utiliser un autre modèle de certificat pour l’autorité de certification sélectionnée** .

7.  Dans la page **Nom et paramètres de sécurité** , procédez comme suit :
    
    1.  Dans **Nom convivial** , tapez un nom d’affichage du certificat.
    
    2.  Dans **Longueur en bits** , spécifiez la longueur en bits (la valeur par défaut est 2048).
    
    3.  Vérifiez que la case **Marquer la clé privée du certificat comme exportable** est cochée.

8.  Dans la page **Informations relatives à l’organisation** , tapez le nom de ’organisation et de l’unité d’organisation (par exemple, une division ou un service).

9.  Dans la page **Informations géographiques** , spécifiez les informations d’emplacement.

10. Dans la page **Nom du sujet/Autres noms du sujet** , le système affiche les informations automatiquement fournies par l’Assistant. Si d’autres noms du sujet doivent être ajoutés, spécifiez-les dans les deux étapes suivantes.

11. Dans la page **Paramètre du domaine SIP sur les autres noms du sujet** , cochez la case du domaine pour ajouter une entrée sip.\<sipdomain\> (domaine SIP) à la liste des autres noms du sujet.

12. Dans la page **Configurer d’autres noms du sujet supplémentaires** , spécifiez les autres noms du sujet supplémentaires nécessaires.
    
    > [!TIP]  
    > Si le proxy XMPP est installé, le nom de domaine par défaut (par exemple, contoso.com) est mentionné dans les entrées du SAN. Si vous nécessitez d’autres entrées, ajoutez-les pendant cette étape.

13. Dans la page **Résumé de la demande** , vérifiez les informations de certificat à utiliser pour générer la demande.

14. Une fois l’exécution des commandes terminée, vous pouvez **Afficher le journal** ou cliquer sur **Suivant** pour continuer.

15. Dans la page **Fichier de demande de certificat** , vous pouvez afficher le fichier de demande de signature de certificat (CSR) généré en cliquant sur Afficher ou quitter l’Assistant Certificat en cliquant sur **Terminer** .

16. Copiez le fichier de la demande et transmettez-le à votre autorité de certification publique.

17. Après la réception, l’importation et l’affectation du certificat public, vous devez redémarrer les services du serveur Edge. Pour cela, tapez dans la console de gestion Lync Server.
    
    ```
    Stop-CsWindowsService
    ```
    ```
    Start-CsWindowsService
    ```

## Configurer une nouvelle passerelle XMPP Lync Server 2013

1.  Ouvrez le Panneau de configuration Lync Server.

2.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe** , puis sur **Partenaires fédérés XMPP** .

3.  Pour créer une configuration, cliquez sur **Nouvelle** .

4.  Définissez les paramètres suivants :

5.  **Domaine principal**     (Obligatoire). Le domaine principal correspond au domaine de base du partenaire XMPP. Par exemple, vous pouvez entrer **fabrikam.com** comme nom de domaine du partenaire XMPP. Cette entrée est obligatoire.

6.  **Description**    La description correspond aux commentaires ou autres informations d’identification de la configuration particulière. Cette entrée est facultative.

7.  **Autres domaines**    domaines faisant partie du domaine de votre partenaire XMPP et qui doivent être intégrés aux communications XMPP autorisées. Par exemple, si le domaine principal correspond à **fabrikam.com**, vous devez alors afficher tous les autres domaines qui se trouvent sous fabrikam.com avec lesquels communiquer par XMPP.

8.  **Type de partenaire**    Le **Type de partenaire** est un paramètre obligatoire. Vous devez choisir l’une des options suivantes pour décrire et appliquer les contacts pouvant être ajoutés. Vous pouvez sélectionner l’une des options suivantes :
    
      - **Fédéré**    Un type de partenaire **fédéré** représente un niveau de confiance élevé entre le déploiement Lync Server et le partenaire XMPP. Ce type de partenaire est recommandé pour la fédération avec des serveurs XMPP dans la même entreprise ou si une relation entre entreprises est établie. Les contacts XMPP au sein des partenaires fédérés peuvent :
        
        1.  ajouter des contacts Lync et afficher leur présence sans autorisation explicite de l’utilisateur de Lync ;
        
        2.  envoyer des messages instantanés aux contacts Lync, que l’utilisateur de Lync les ait ajoutés à leur liste des contacts ou non ;
        
        3.  afficher les notes de statut de l’utilisateur de Lync.
    
      - **Public vérifié**    Un partenaire **Public vérifié** est un fournisseur XMPP public fiable chargé de vérifier l’identité de ses utilisateurs. Les contacts XMPP dans les réseaux Public vérifié peuvent ajouter des contacts Lync, afficher la présence de ces derniers et leur envoyer des messages instantanés sans autorisation explicite des utilisateurs de Lync. Les contacts XMPP dans les réseaux Public vérifié ne peuvent jamais afficher les notes de statut des utilisateurs de Lync. Ce paramètre n’est pas recommandé.
    
      - **Public non vérifié**    Un partenaire **Public non vérifié** est un fournisseur XMPP qui n’est pas considéré comme fiable pour vérifier l’identité de ses utilisateurs. Les utilisateurs XMPP dans les réseaux Public non vérifié ne peuvent pas communiquer avec les utilisateurs de Lync sauf si l’utilisateur de Lync les a autorisés de façon explicite à les ajouter à la liste des contacts. Les utilisateurs XMPP dans les réseaux Public vérifié ne peuvent jamais afficher les notes de statut des utilisateurs de Lync. Ce paramètre est recommandé pour toutes les fédérations avec des fournisseurs XMPP publics comme Google Talk.

9.  **Type de connexion :** définit les différentes règles et paramètres de rappel.
    
      - **Négociation TLS** Définit les règles de négociation TLS. Un service XMPP peut nécessiter TLS, peut rendre TLS facultatif ou vous pouvez indiquer que TLS n’est pas pris en charge. Si vous choisissez Facultatif, c’est le service XMPP qui décide de son caractère obligatoire pour la négociation. Pour afficher tous les paramètres possibles et les détails pour la négociation SASL, TLS et Dialback (notamment les configurations incorrectes et les erreurs connues), reportez-vous à [Paramètres de négociation pour les partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)
        
          -   
            **Obligatoire**    Le service XMPP nécessite la négociation TLS.
        
          -   
            **Facultatif**    Le service XMPP indique que TLS est obligatoire pour la négociation.
        
          -   
            **Non pris en charge**    Le service XMPP ne prend pas en charge TLS.
    
      - **Négociation SASL**    Définit les règles de négociation SASL. Un service XMPP peut nécessiter SASL, peut rendre SASL facultatif ou vous pouvez décider de ne pas prendre en charge SASL. Si vous choisissez Facultatif, le service XMPP est responsable de la décision sur la négociation obligatoire.
        
          -   
            **Obligatoire**    Le service XMPP nécessite la négociation SASL.
        
          -   
            **Facultatif**    Le service XMPP indique que SASL est obligatoire pour la négociation.
        
          -   
            **Non pris en charge**    Le service XMPP ne prend pas en charge SASL.
    
      - **Prendre en charge la négociation de rappel du serveur** Le processus de prise en charge de Server Dialback Negotiation utilise le système DNS (Domain Name System) et un serveur de référence pour vous assurer que la demande provient d’un partenaire XMPP valide. Pour cela, le serveur d’origine crée un message d’un type particulier à l’aide d’une clé de rappel générée et recherche le serveur en réception dans DNS. Le serveur d’origine envoie la clé dans un flux XML au résultat de la recherche DNS obtenue, a priori le serveur en réception. À la réception de la clé par le flux XML, le serveur destinataire ne répond pas au serveur d’origine, mais envoie la clé à un serveur de référence connu. Le serveur de référence vérifie que la clé est valide. Si elle ne l’est pas, le serveur en réception ne répond pas au serveur d’origine. Si la clé est valide, le serveur en réception informe le serveur d’origine que l’identité et la clé sont valides. La conversation peut alors commencer.
        
        Il existe deux états valides pour la **négociation de rappel** :
        
          -   
            **Vrai**    Le serveur XMPP est configuré pour utiliser la négociation de rappel si une demande doit être reçue d’un serveur d’origine.
        
          -   
            **Faux**    Le serveur XMPP n’est pas configuré pour utiliser la négociation de rappel. Si une demande doit être reçue d’un serveur d’origine, elle est alors ignorée.

10. Cliquez sur **Valider** pour enregistrer vos modifications du site ou de la stratégie de l’utilisateur.

## Mettre à jour des enregistrements DNS pour la passerelle XMPP de Lync Server 2013

1.  Pour configurer le DNS pour la fédération XMPP, vous devez ajouter l’enregistrement SRV suivant à votre DNS:\_xmpp-server.\_tcp.\<nom de domaine\> externe. L’enregistrement SRV se résout en nom de domaine complet du serveur Edge d’accès, avec une valeur de port de 5269.

