---
title: 'Lync Server 2013 : Configuration de la fédération XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd61aded33d37e4a1f5f58e9050f3cd62794f9b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a>Configuration de la fédération XMPP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-12-03_

Pour déployer le proxy XMPP sur le serveur Edge, vous devez configurer le serveur Edge pour la Fédération XMPP. Pour cela, procédez comme suit.

<div>

## <a name="setting-up-xmpp-federation"></a>Configuration de la Fédération XMPP

1.  Ouvrez une session sur l’ordinateur sur lequel est installé l’Assistant Déploiement de Lync Server en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.

2.  Sur le serveur frontal, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur installer ou mettre à jour le système serveur Lync, puis cliquez sur Configurer ou supprimer les composants Lync Server. Cliquez de nouveau sur Exécuter.

3.  Dans configurer les composants serveur Lync, cliquez sur suivant. L’écran de synthèse indique les actions à mesure qu’elles sont exécutées. Lorsque le déploiement est effectué, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles. Cliquez sur Terminer pour terminer le déploiement.

4.  Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur installer ou mettre à jour le système serveur Lync, puis cliquez sur Configurer ou supprimer les composants Lync Server. Cliquez de nouveau sur Exécuter.

5.  Dans configurer les composants serveur Lync, cliquez sur suivant. L’écran de synthèse indique les actions à mesure qu’elles sont exécutées. Lorsque le déploiement est effectué, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles. Cliquez sur Terminer pour terminer le déploiement.

6.  Sur le serveur Edge, dans l’Assistant Déploiement, en regard de l’étape 3 : demandez, installez ou attribuez des certificats, cliquez de nouveau sur Exécuter.
    
    <div class=" ">
    

    > [!TIP]  
    > Si vous déployez le serveur Edge pour la première fois, vous verrez exécuter au lieu de réexécuter.

    
    </div>

7.  Dans la page Tâches se rapportant aux certificats disponibles, cliquez sur Créer une demande de certificat.

8.  Dans la page demande de certificat, cliquez sur certificat de bord externe.

9.  Dans la page de demande retardée ou immédiate, activez la case à cocher préparer la demande maintenant, puis l’envoyer plus tard.

10. Dans la page fichier de demande de certificat, tapez le chemin d’accès complet et le nom du fichier dans lequel la demande doit être enregistrée (par exemple,\\c\_:\_CERT l’Edge. cer).

11. Dans la page spécifier un modèle de certificat secondaire, pour utiliser un modèle autre que le modèle par défaut du serveur Web, activez la case à cocher utiliser un autre modèle de certificat pour l’autorité de certification sélectionnée.

12. Dans la page Nom et paramètres de sécurité, procédez comme suit :
    
    1.  Dans nom convivial, tapez un nom d’affichage pour le certificat.
    
    2.  En longueur, spécifiez la longueur en bits (en général, la valeur par défaut 2048)
    
    3.  Vérifier que la case à cocher marquer le certificat privé comme étant exportable est activée

13. Dans la page informations sur l’organisation, tapez le nom de l’organisation et celle de l’unité d’organisation (par exemple, une division ou un service).

14. Dans la page informations géographiques, spécifiez les informations d’emplacement

15. Sur la page nom de l’objet/nom de l’objet, les informations à remplir automatiquement par l’Assistant sont affichées. Si d’autres noms d’objet sont nécessaires, vous pouvez les spécifier au cours des deux étapes suivantes.

16. Dans la page Configuration du protocole SIP sur le nom de l’objet, activez la case à cocher Domain pour ajouter un SIP. \<entrée\> sipdomain dans la liste noms de remplacement de l’objet.

17. Dans la page configurez d’autres noms d’objet, spécifiez d’autres noms d’objet requis
    
    <div class=" ">
    

    > [!TIP]  
    > Si le proxy XMPP est installé, le nom de domaine par défaut (par exemple, contoso.com) est renseigné dans les entrées du SAN. Si vous avez besoin d’entrées supplémentaires, ajoutez-les à cette étape.

    
    </div>

18. Dans la page Résumé de la demande, passez en revue les informations de certificat à utiliser pour générer la requête.

19. À la fin de l’exécution des commandes, vous pouvez consulter le journal ou cliquer sur suivant pour continuer.

20. Dans la page fichier de demande de certificat, vous pouvez afficher le fichier de demande de signature de certificat généré (CSR) en cliquant sur Afficher ou quitter l’Assistant Certificat en cliquant sur Terminer.

21. Copiez le fichier de demande et envoyez-le à votre autorité de certification publique.

22. Après avoir reçu, importé et attribué le certificat public, vous devez arrêter et redémarrer les services Edge Server. Pour cela, entrez dans la console de gestion de Lync Server :
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. Pour configurer le système DNS pour la Fédération XMPP, ajoutez l’enregistrement SRV suivant à DNS\_externe : XMPP-Server. \_TCP. \<nom de\> domaine l’enregistrement SRV sera résolu vers le nom de domaine complet d’accès du serveur Edge, avec une valeur de port de 5269. Par ailleurs, vous configurez un enregistrement hôte « A » (par exemple, xmpp.contoso.com) qui pointe vers l’adresse IP du serveur Edge d’accès.
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Si vous disposez de pools de périphérie dans plusieurs sites, nous vous recommandons d’ajouter plusieurs enregistrements SRV pour la Fédération XMPP. Ajoutez un enregistrement SRV pour chaque pool de périphérie de votre organisation et attribuez à chacun de ces enregistrements SRV une priorité différente. Lorsque tous les pools d’arêtes sont en cours d’exécution, les demandes XMPP seront gérées par le pool de bords avec la première priorité, mais si le pool de bords devient inactif, vous n’aurez pas besoin d’ajouter un nouvel enregistrement SRV pour restaurer la fonctionnalité de Fédération XMPP.

    
    </div>

24. Configurez une nouvelle stratégie d’accès externe pour permettre à tous les utilisateurs d’ouvrir Lync Server Management Shell sur le front end et de taper :
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    Activez l’accès XMPP pour les utilisateurs externes en entrant :
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. Sur le serveur Edge sur lequel est déployé le proxy XMPP, ouvrez une invite de commandes ou une interface de ligne de commande™ Windows PowerShell, puis tapez les informations suivantes :
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    La commande **netstat-ano** est une commande statistiques réseau, les paramètres **-ano** , qui affiche la totalité des connexions et des ports d’écoute, l’adresse et les ports sont affichés sous la forme d’une forme numérique et que l’ID du processus propriétaire est associé à chaque connexion. Le caractère **|** définit un canal sur la commande suivante, **findstr**ou rechercher une chaîne. Le nombre 5269 et 23456 transmis à FINDSTR en tant que paramètre indiquent à findstr d’effectuer une recherche dans la sortie de netstat pour les chaînes 5269 et 23456. Si XMPP est configuré correctement, le résultat des commandes doit avoir pour effet d’écouter les connexions d’écoute et de connexion établie, à la fois sur les interfaces externes (port 5269) et internes (port 23456) du serveur Edge.
    
    Si les commandes ne renvoient pas de ports établis ou en écoute sur 5269 et 23456, vérifiez les points suivants :

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a>Résoudre les problèmes de Fédération XMPP

1.  Pour déterminer si le proxy XMPP est en cours d’exécution, procédez comme suit :

2.  Ouvrez une session sur le serveur Edge qui exécute le service proxy XMPP en tant que membre du groupe de l’administrateur local.

3.  Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Outils d’administration**, puis sur **services** .

4.  Dans services, recherchez proxy Lync Server XMPP traduction de la passerelle proxy. Le service doit être au mode **démarré** . Si ce n’est pas le cas, cliquez sur l’icône **Démarrer** dans la barre d’outils. L’icône s’affiche sous la forme d’une flèche verte vers la droite.

5.  Vérifiez que le service a changé pour **démarré**. Si le problème persiste, fermez les **services** et continuez.
    
    Si le service n’a pas réussi à démarrer, dans les outils d’administration, ouvrez l’observateur d’événements, puis référez-vous aux erreurs et avertissements dans la partie **serveur Lync** sous **journaux des applications et des services**.

6.  Lorsque le service **passerelle de traduction de Lync Server XMPP** est en cours d’exécution, revérifiez les commandes netstat utilisées précédemment. Si vous ne voyez pas les sessions établies ou écoutées, vérifiez et assurez-vous que l' **itinéraire de Fédération XMPP** est correctement configuré dans le générateur de topologie.

7.  Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.

8.  Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.

9.  Dans le générateur de topologie, sélectionnez le site pour le routage de Fédération XMPP et l’avis pour vérifier que l’affectation de l’itinéraire de la **Fédération de site** pour la **Fédération XMPP** indique votre serveur Edge ou votre pool Edge en tant qu’attribution de l’itinéraire de Fédération XMPP sélectionnée.
    
    Si l’affectation de l’itinéraire est incorrecte ou n’est pas définie, cliquez avec le bouton droit sur le site, puis cliquez sur **modifier les propriétés**. Activez la case à cocher Fédération XMPP, puis sélectionnez le serveur Edge ou le pool de bords approprié.

10. Publiez la topologie. Pour plus d’informations, reportez-vous à [la rubrique publier votre topologie dans Lync Server 2013](lync-server-2013-publish-your-topology.md)
    
    <div class=" ">
    

    > [!TIP]  
    > Même si ce n’est pas obligatoire et n’est généralement pas nécessaire, il est possible que vous deviez redémarrer les serveurs Edge.

    
    </div>

11. À l’aide du processus netstat utilisé précédemment, vérifiez que le serveur Edge écoute ou a établi des sessions sur le port 5269 et le port 23456.

12. Si vous ne voyez toujours pas les sessions attendues, consultez l’observateur d’événements pour connaître les causes possibles du problème de communication.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Gestion des partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

