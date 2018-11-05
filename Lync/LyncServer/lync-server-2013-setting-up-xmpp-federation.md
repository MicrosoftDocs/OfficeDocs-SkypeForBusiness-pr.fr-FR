---
title: 'Lync Server 2013 : Configuration de la fédération XMPP'
TOCTitle: Configuration de la fédération XMPP
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204939(v=OCS.15)
ms:contentKeyID: 49297371
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la fédération XMPP dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-12-03_

Pour déployer le proxy XMPP sur le serveur Edge, vous devez configurer le serveur Edge pour la fédération XMPP. Pour cela, effectuez les étapes suivantes.

## Configuration de la fédération XMPP

1.  Ouvrez une session sur l’ordinateur sur lequel l’Assistant Déploiement de Lync Server est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.

2.  Sur le serveur frontal, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur Installer ou mettre à jour le système Lync Server, puis sur Installer ou supprimer des composants Lync Server. Cliquez sur Réexécuter.

3.  Dans Installer les composants Lync Server, cliquez sur Suivant. L’écran récapitulatif affiche les actions au fur et à mesure qu’elles s’exécutent. Une fois le déploiement terminé, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles. Cliquez sur Terminer pour terminer le déploiement.

4.  Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur Installer ou mettre à jour le système Lync Server, puis sur Installer ou supprimer des composants Lync Server. Cliquez sur Réexécuter.

5.  Dans Installer les composants Lync Server, cliquez sur Suivant. L’écran récapitulatif affiche les actions au fur et à mesure qu’elles s’exécutent. Une fois le déploiement terminé, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles. Cliquez sur Terminer pour terminer le déploiement.

6.  Sur le serveur Edge, dans l’Assistant Déploiement, en regard de Étape 3 : Demander, installer ou affecter les certificats, cliquez sur Réexécuter.
    
    > [!TIP]  
    > Si vous déployez pour la première fois le serveur Edge, l’option Exécuter s’affiche au lieu de Réexécuter.

7.  Dans la page Tâches se rapportant aux certificats disponibles, cliquez sur Créer une demande de certificat.

8.  Dans la page Demande de certificat, cliquez sur Certificat de serveur Edge externe.

9.  Dans la page Demande différée ou immédiate, cochez la case Préparer la demande maintenant, mais l’envoyer plus tard.

10. Dans la page Fichier de demande de certificat, tapez le chemin d’accès complet et le nom du fichier dans lequel la demande doit être enregistrée (par exemple, c:\\cert\_exernal\_edge.cer).

11. Dans la page Spécifier un autre modèle de certificat, pour utiliser un autre modèle que le modèle WebServer par défaut, cochez la case Utiliser un autre modèle de certificat pour l’autorité de certification sélectionnée.

12. Dans la page Nom et paramètres de sécurité, procédez comme suit :
    
    1.  Dans Nom convivial, tapez un nom d’affichage pour le certificat.
    
    2.  Dans Longueur en bits, spécifiez la longueur en bits (en général, la valeur par défaut est 2 048).
    
    3.  Vérifiez que la case à cocher Marquer la clé privée du certificat comme exportable est activée.

13. Dans la page Informations relatives à l’organisation, tapez le nom de l’organisation et de l’unité d’organisation (par exemple, une division ou un service).

14. Dans la page Informations géographiques, spécifiez les informations d’emplacement.

15. Dans la page Nom du sujet/Autres noms du sujet, le système affiche les informations automatiquement renseignées par l’Assistant. Si d’autres noms du sujet doivent être ajoutés, spécifiez-les lors des deux étapes suivantes.

16. Dans la page Paramètre du domaine SIP sur les autres noms du sujet, cochez la case du domaine pour ajouter une entrée sip.\<sipdomain\> (domaine SIP) à la liste des autres noms du sujet.

17. Dans la page Configurer d’autres noms du sujet supplémentaires, spécifiez les autres noms du sujet supplémentaires requis.
    
    > [!TIP]  
    > Si le proxy XMPP est installé, le nom de domaine par défaut (par exemple, contoso.com) est mentionné dans les entrées du SAN. Si vous nécessitez d’autres entrées, ajoutez-les pendant cette étape.

18. Dans la page Résumé de la demande, vérifiez les informations de certificat à utiliser pour générer la demande.

19. Une fois les commandes entièrement exécutées, vous pouvez Afficher le journal ou cliquer sur Suivant pour continuer.

20. Dans la page Fichier de demande de certificat, vous pouvez afficher le fichier de demande de signature de certificat (CSR) généré en cliquant sur Afficher ou quitter l’Assistant Certificat en cliquant sur Terminer .

21. Copiez le fichier de la demande et transmettez-le à votre autorité de certification publique.

22. Après la réception, l’importation et l’affectation du certificat public, vous devez redémarrer les services du serveur Edge. Pour cela, tapez dans la console de gestion Lync Server.
    
    ```
    Stop-CsWindowsService
    ```
    ```
    Start-CsWindowsService
    ```

23. Pour configurer DNS pour la fédération XMPP, vous devez ajouter l’enregistrement SRV suivant au système DNS externe :\_xmpp-server.\_tcp.\<nom de domaine\> L’enregistrement SRV aboutira au nom de domaine complet du service Edge, avec une valeur de port de 5 269. Par ailleurs, vous devez configurer un enregistrement d’hôte « A » (par exemple, xmpp.contoso.com) qui pointe vers l’adresse IP du serveur Edge d’accès.
    
    > [!IMPORTANT]  
    > Si vous avez des pools de serveurs Edge dans plusieurs sites, nous vous recommandons d’ajouter plusieurs enregistrements SRV pour la fédération XMPP. Ajoutez un enregistrement SRV pour chaque pool de serveurs Edge dans votre organisation, puis donnez à chacun de ces enregistrements SRV une priorité différente. Lorsque tous les pools de serveurs Edge sont en cours d’exécution, les demandes XMPP sont toutes traitées par le pool de serveurs Edge de première priorité. Cependant, si ce pool de serveurs Edge ne fonctionne pas, vous n’êtes pas obligé d’ajouter un enregistrement SRV pour rétablir les fonctionnalités de fédération XMPP.

24. Configurez une nouvelle stratégie d’accès externe pour activer tous les utilisateurs en ouvrant Lync Server Management Shell sur le serveur frontal et en tapant :
    
    ```
    New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
    ```
    ```
    New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
    ```
    ```
    Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
    ```

    Activez l’accès XMPP pour les utilisateurs externes en tapant :
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
    ```
    ```
    Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
    ```

25. Sur le serveur Edge où le proxy XMPP est déployé, ouvrez une invite de commandes ou une interface de ligne de commande Windows PowerShell™, puis tapez ce qui suit :
    
    ```
    Netstat -ano | findstr 5269
    ```
    ```
    Netstat -ano | findstr 23456
    ```
    
    La commande **netstat –ano** est une commande de statistiques réseau. Les paramètres **–ano** exigent que netstat affiche tous les ports d’écoute et connexions, que l’adresse et les ports s’affichent sous forme numérique, et que l’ID du processus propriétaire soit associé à chaque connexion. Le caractère **|** définit un canal vers la commande suivante, **findstr**, ou recherche la chaîne. Les valeurs 5269 et 23456 transmises à findstr sous forme de paramètre lui indiquent de rechercher les chaînes 5269 et 23456 dans les résultats de netstat. Si XMPP est bien configuré, le résultat des commandes doit aboutir à des connexions établies et d’écoute, à la fois sur les interfaces externes (port 5269) et internes (port 23456) du serveur Edge.
    
    Si les commandes ne renvoient pas des ports établis ou d’écoute sur 5269 et 23456, examinez ce qui suit :

## Identification et résolution des problèmes liés à la fédération XMPP

1.  Pour déterminer si le proxy XMPP est en cours d’exécution, procédez comme suit :

2.  Ouvrez une session sur le serveur Edge qui exécute le service proxy XMPP en tant que membre du groupe Administrateurs local.

3.  Cliquez sur **Démarrer** , sur **Tous les programmes** , sur **Outils d’administration** , puis sur **Services** .

4.  Dans Services, recherchez Proxy de passerelle de conversion XMPP de Lync Server. Le service doit avoir l’état **Démarré** . S’il n’est pas démarré, cliquez sur l’icône **Démarrer** dans la barre d’outils. L’icône s’affiche sous la forme d’une flèche verte pointant vers la droite.

5.  Confirmez que le service a bien l’état **Démarré** . S’il a correctement démarré, fermez **Services** et continuez.
    
    Si le service n’a pas correctement démarré, dans Outils d’administration, ouvrez l’observateur d’événements et passez en revue les erreurs et les avertissements contenus dans la partie **Lync Server** sous **Journaux des applications et des services** .

6.  Une fois que le service **Passerelle de conversion XMPP de Lync Server** est en cours d’exécution, revérifiez les commandes netstat utilisées précédemment. Si vous ne voyez pas de sessions établies ou d’écoute, assurez-vous que l’**Itinéraire de fédération XMPP** est correctement configuré dans le Générateur de topologie.

7.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologie est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.

8.  Démarrez le Générateur de topologie : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Générateur de topologie Lync Server**.

9.  Dans le Générateur de topologie, sélectionnez le site pour l’itinéraire de fédération XMPP et confirmez que l’**Attribution de l’itinéraire de fédération du site** pour la **Fédération XMPP** indique que votre serveur Edge ou votre pool de serveurs Edge est bien l’attribution de l’itinéraire de fédération XMPP sélectionnée.
    
    Si l’attribution de l’itinéraire est incorrecte ou n’est pas définie, cliquez avec le bouton droit sur le site, cliquez sur **Modifier les propriétés** . Activez la case à cocher Fédération XMPP, puis sélectionnez le serveur Edge ou le pool de serveurs Edge approprié.

10. Publiez la topologie. Pour plus d’informations, reportez-vous à [Publication de la topologie dans Lync Server 2013](lync-server-2013-publish-your-topology.md).
    
    > [!TIP]  
    > Même si, en général, cela n’est pas nécessaire, il est possible que vous soyez amené à redémarrer les serveurs Edge.

11. Selon le processus netstat utilisé précédemment, confirmez que le serveur Edge est maintenant à l’écoute ou qu’il dispose de sessions établies sur les ports 5269 et 23456.

12. Si vous ne voyez toujours pas les sessions attendues, passez en revue l’observateur d’événements pour tenter de trouver les causes possibles de ce problème de communication.

## Voir aussi

#### Tâches

[Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### Autres ressources

[Gestion des partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

