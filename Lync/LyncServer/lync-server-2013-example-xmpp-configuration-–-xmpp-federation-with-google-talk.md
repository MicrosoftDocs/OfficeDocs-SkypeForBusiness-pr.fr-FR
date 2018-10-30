---
title: "Lync Server 2013 : Ex. de conf.n XMPP – Fédération XMPP avec Google Talk"
TOCTitle: Exemple de configuration XMPP – Fédération XMPP avec Google Talk
ms:assetid: 360a2f7b-015b-4e93-ac67-0f609c21f1a2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204807(v=OCS.15)
ms:contentKeyID: 49296845
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk

 

_**Dernière rubrique modifiée :** 2016-12-08_

Voici un exemple de configuration pour le déploiement du proxy XMPP qui définit une fédération avec Google Talk.

## Exemple de configuration XMPP – Fédération XMPP avec Google Talk

1.  Sur le serveur frontal, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur **Installer** ou **mettre à jour le système Lync Server** , puis sur **Installer** ou **supprimer des composants Lync Server** . Cliquez sur **Réexécuter** .

2.  Dans **Installer les composants Lync Server** , cliquez sur **Suivant** . L’écran récapitulatif affiche les actions au fur et à mesure qu’elles s’exécutent. Une fois le déploiement terminé, cliquez sur **Afficher le journal** pour afficher les fichiers journaux disponibles. Cliquez sur **Terminer** pour terminer le déploiement.

3.  Sur le serveur Edge, ouvrez le Assistant Déploiement de Lync Server. Cliquez sur **Installer** ou **Mettre à jour le système Lync Server**, puis sur **Installer** ou **Supprimer des composants Lync Server**. Cliquez sur **Réexécuter**.

4.  Ajoutez Google Talk en tant que partenaire XMPP autorisé. Google Talk ne prend actuellement en charge que les connexions TCP non chiffrées pour la fédération XMPP serveur à serveur et ne prend en charge que le Server Dialback pour la vérification d’identité. (Reportez-vous à <http://xmpp.org/extensions/xep-0220.html>).
    
        New-CsXmppAllowedPartner gmail.com -TlsNegotiation NotSupported -SaslNegotiation NotSupported -EnableKeepAlive $false -SupportDialbackNegotiation $true

5.  Pour activer la fédération Edge, tapez ce qui suit :
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $true

6.  Dans **Installer les composants Lync Server** , cliquez sur **Suivant** . L’écran récapitulatif affiche les actions au fur et à mesure qu’elles s’exécutent. Une fois le déploiement effectué, cliquez sur **Afficher le journal** pour afficher les fichiers journaux disponibles. Cliquez sur **Terminer** pour terminer le déploiement.

7.  Sur le serveur Edge, dans l’Assistant Déploiement de Lync Server, en regard de **Étape 3 : Demander, installer ou affecter des certificats** , cliquez sur **Réexécuter** .
    
    > [!TIP]  
    > Si vous déployez pour la première fois le serveur Edge, l’option Exécuter s’affiche au lieu de Réexécuter.


8.  Dans la page **Tâches se rapportant aux certificats disponibles** , cliquez sur **Créer une demande de certificat** .

9.  Dans la page **Demande de certificat** , cliquez sur **Certificat de serveur Edge externe** .

10. Dans la page **Demande différée ou immédiate** , cochez la case **Préparer la demande maintenant, mais l’envoyer plus tard** .

11. Dans la page **Fichier de demande de certificat** , tapez le chemin d’accès complet et le nom du fichier dans lequel la demande doit être enregistrée (par exemple, c:\\cert\_exernal\_edge.cer).

12. Dans la page **Spécifier un autre modèle de certificat** , pour utiliser un autre modèle que le modèle WebServer par défaut, cochez la case **Utiliser un autre modèle de certificat pour l’autorité de certification sélectionnée** .

13. Dans la page **Nom et paramètres de sécurité** , procédez comme suit :
    
    1.  Dans **Nom convivial** , tapez un nom d’affichage pour le certificat.
    
    2.  Dans **Longueur en bits** , spécifiez la longueur en bits (généralement, la valeur par défaut est **2048** ).
    
    3.  Vérifiez que la case à cocher **Marquer la clé privée du certificat comme exportable** est activée.

14. Dans la page **Informations relatives à l’organisation** , tapez le nom de l’organisation et de l’unité d’organisation (par exemple, une division ou un service)

15. Dans la page **Informations géographiques** , spécifiez les informations d’emplacement

16. Dans la page **Nom du sujet/Autres noms du sujet** , le système affiche les informations automatiquement renseignées par l’Assistant. Si d’autres noms du sujet doivent être ajoutés, spécifiez-les lors des deux étapes suivantes.

17. Dans la page **Paramètre du domaine SIP sur les autres noms du sujet** , activez la case à cocher du domaine pour ajouter une entrée sip. *\<sipdomain\>* (domaine SIP) à la liste des autres noms du sujet.

18. Dans la page **Configurer d’autres noms du sujet supplémentaires** , spécifiez les autres noms du sujet supplémentaires nécessaires.
    
    > [!TIP]  
    > Si le proxy XMPP est installé, le nom de domaine par défaut (par exemple, contoso.com) est mentionné dans les entrées du SAN. Si vous nécessitez d’autres entrées, ajoutez-les pendant cette étape.


19. Dans la page **Résumé de la demande** , vérifiez les informations de certificat à utiliser pour générer la demande.

20. Une fois l’exécution des commandes terminée, vous pouvez **Afficher le journal** ou cliquer sur **Suivant** pour continuer.

21. Dans la page **Fichier de demande de certificat** , vous pouvez afficher le fichier de demande de signature de certificat (CSR) généré en cliquant sur **Afficher** ou quitter l’Assistant Certificat en cliquant sur **Terminer** .

22. Copiez le fichier de la demande et transmettez-le à votre autorité de certification publique.

23. Après avoir reçu, importé et affecté le certificat public, vous devez arrêter et redémarrer les services du serveur Edge. Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.. Dans Lync Server Management Shell, tapez :
    
    ```
    Stop-CsWindowsService
    ```
    ```
    Start-CsWindowsService
    ```

24. Pour configurer les DNS pour la fédération XMPP, vous devez ajouter l’enregistrement SRV suivant au système DNS externe :\_xmpp-server.\_tcp. *\<nom de domaine\>* . L’enregistrement SRV résoudra le nom complet de domaine du serveur Edge d’accès, avec une valeur de port de 5 269

25. Pour configurer une nouvelle stratégie d’accès externe afin d’activer tous les utilisateurs, ouvrez Lync Server Management Shell sur un serveur frontal et tapez :
    
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAccess $true -EnablePublicCloudAccess $true
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic

