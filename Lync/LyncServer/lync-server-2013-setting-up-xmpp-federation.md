---
title: 'Lync Server 2013 : configuration de la Fédération XMPP'
description: 'Lync Server 2013 : configuration de la Fédération XMPP.'
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
ms.openlocfilehash: b8a1fa15e399b0e0596a697420042b7504f8b791
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555700"
---
# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a>Configuration de la Fédération XMPP dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-12-03_

Pour déployer le proxy XMPP sur le serveur Edge, vous devez configurer le serveur Edge pour la fédération XMPP. Pour cela, effectuez les étapes suivantes.

<div>

## <a name="setting-up-xmpp-federation"></a>Configuration de la fédération XMPP

1.  Ouvrez une session sur l’ordinateur sur lequel l’Assistant Déploiement de Lync Server est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.

2.  Sur le serveur frontal, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur Installer ou mettre à jour le système Lync Server, puis sur Installer ou supprimer des composants Lync Server. Cliquez sur Réexécuter.

3.  Dans Installer les composants Lync Server, cliquez sur Suivant. L’écran de résumé affiche les actions au fur et à mesure qu’elles s’exécutent. Une fois le déploiement terminé, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles. Cliquez sur Terminer pour terminer le déploiement.

4.  Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur Installer ou mettre à jour le système Lync Server, puis sur Installer ou supprimer des composants Lync Server. Cliquez sur Réexécuter.

5.  Dans Installer les composants Lync Server, cliquez sur Suivant. L’écran de résumé affiche les actions au fur et à mesure qu’elles s’exécutent. Une fois le déploiement terminé, cliquez sur Afficher le journal pour afficher les fichiers journaux disponibles. Cliquez sur Terminer pour terminer le déploiement.

6.  Sur le serveur Edge, dans l’Assistant Déploiement, en regard de Étape 3 : Demander, installer ou assigner les certificats, cliquez sur Réexécuter.
    
    <div class=" ">
    

    > [!TIP]  
    > Si vous déployez le serveur Edge pour la première fois, Exécuter figure à la place de Réexécuter.

    
    </div>

7.  Dans la page Tâches se rapportant aux certificats disponibles, cliquez sur Créer une nouvelle demande de certificat.

8.  Sur la page demande de certificat, cliquez sur certificat de serveur Edge externe.

9.  Dans la page Demande différée ou immédiate, activez la case à cocher Préparer la demande maintenant, mais l’envoyer plus tard.

10. Dans la page fichier de demande de certificat, tapez le chemin d’accès complet et le nom du fichier dans lequel la demande doit être enregistrée (par exemple, c : \\ CERT \_ exernal \_ Edge. cer).

11. Dans la page Spécifier un autre modèle de certificat, pour utiliser un autre modèle que le modèle Serveur web par défaut, activez la case à cocher Utiliser un autre modèle de certificat pour l’autorité de certification sélectionnée.

12. Dans la page Nom et paramètres de sécurité, procédez comme suit :
    
    1.  Dans Nom convivial, tapez un nom d’affichage pour le certificat.
    
    2.  Dans Longueur en bits, spécifiez la longueur en bits (en général, la valeur par défaut est 2 048).
    
    3.  Vérifiez que la case à cocher Marquer la clé privée du certificat comme exportable est activée.

13. Dans la page Informations relatives à l’organisation, tapez le nom de l’organisation et de l’unité d’organisation (par exemple, une division ou un service).

14. Dans la page Informations géographiques, spécifiez les informations d’emplacement.

15. Dans la page Nom du sujet/Autres noms du sujet, le système affiche les informations automatiquement renseignées par l’Assistant. Si d’autres noms du sujet doivent être ajoutés, spécifiez-les lors des deux étapes suivantes.

16. Sur la page paramètre du domaine SIP sur les autres noms du sujet, activez la case à cocher domaine pour ajouter un SIP.\<sipdomain\> entrée de la liste des autres noms du sujet.

17. Dans la page Configurer d’autres noms du sujet supplémentaires, spécifiez les autres noms du sujet supplémentaires requis.
    
    <div class=" ">
    

    > [!TIP]  
    > Si le proxy XMPP est installé, par défaut, les entrées SAN sont remplies avec le nom de domaine (par exemple, contoso.com). Si vous avez besoin d’entrées supplémentaires, ajoutez-les dans cette étape.

    
    </div>

18. Dans la page Résumé de la demande, vérifiez les informations de certificat à utiliser pour générer la demande.

19. Une fois l’exécution des commandes terminée, vous pouvez afficher le journal ou cliquer sur Suivant pour continuer.

20. Dans la page Fichier de demande de certificat, vous pouvez afficher le fichier de demande de signature de certificat (CSR) généré en cliquant sur Afficher ou quitter l’Assistant Certificat en cliquant sur Terminer.

21. Copiez le fichier de demande et envoyez-le à l’autorité de certification publique.

22. Après la réception, l’importation et l’affectation du certificat public, vous devez redémarrer les services du serveur Edge. Pour cela, tapez dans la console de gestion Lync Server.
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. Pour configurer DNS pour la Fédération XMPP, vous devez ajouter l’enregistrement SRV suivant à DNS externe : \_ XMPP-Server. \_ TCP.\<domain name\> L’enregistrement SRV est résolu en un nom de domaine complet du serveur Edge d’accès, avec une valeur de port de 5269. Par ailleurs, vous devez configurer un enregistrement d’hôte « A » (par exemple, xmpp.contoso.com) qui pointe vers l’adresse IP du serveur Edge d’accès.
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Si vous avez des pools de serveurs Edge dans plusieurs sites, nous vous recommandons d’ajouter plusieurs enregistrements SRV pour la fédération XMPP. Ajoutez un enregistrement SRV pour chaque pool de serveurs Edge dans votre organisation, puis donnez à chacun de ces enregistrements SRV une priorité différente. Lorsque tous les pools de serveurs Edge sont en cours d’exécution, les demandes XMPP sont toutes traitées par le pool de serveurs Edge de première priorité. Toutefois, si ce pool de serveurs Edge tombe en panne, vous n’êtes pas obligé d’ajouter un enregistrement SRV pour rétablir les fonctionnalités de fédération XMPP.

    
    </div>

24. Configurez une nouvelle stratégie d’accès externe pour activer tous les utilisateurs en ouvrant Lync Server Management Shell sur le serveur frontal et en tapant :
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    Activez l’accès XMPP pour les utilisateurs externes en tapant :
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. Sur le serveur Edge sur lequel le proxy XMPP est déployé, ouvrez une invite de commandes ou une interface de ligne de commande™ Windows PowerShell, puis tapez ce qui suit :
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    La commande **netstat –ano** est une commande de statistiques réseau, la paramètres **–ano** demandent que netstat affiche la totalité des connexions et des ports d’écoute, que l’adresse et les ports soient affichés sous forme numérique, et que l’ID du processus propriétaire soit associé à chaque connexion. Le caractère **|** définit un canal pour la commande suivante, **findstr**ou rechercher une chaîne. Le nombre 5269 et 23456 transmis à FINDSTR en tant que paramètre demande à findstr de rechercher la sortie de netstat pour les chaînes 5269 et 23456. Si XMPP est correctement configuré, le résultat des commandes doit aboutir à des connexions d’écoute et établies, à la fois sur les interfaces externe (port 5269) et interne (port 23456) du serveur Edge.
    
    Si les commandes ne retournent pas des ports établis ou d’écoute sur 5269 et 23456, examinez ce qui suit :

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a>Dépannage de la fédération XMPP

1.  Pour déterminer si le proxy XMPP est en cours d’exécution, procédez comme suit :

2.  Ouvrez une session sur le serveur Edge qui exécute le service proxy XMPP en tant que membre du groupe Administrateurs local.

3.  Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Outils d’administration**, puis sur **Services**.

4.  Dans Services, recherchez Proxy de passerelle de traduction XMPP de Lync Server. Le service doit avoir l’état **Démarré**. S’il n’est pas démarré, cliquez sur l’icône **Démarrer** dans la barre d’outils. L’icône apparaît sous la forme d’une flèche verte pointant vers la droite.

5.  Confirmez que le service a bien l’état **Démarré**. S’il a correctement démarré, fermez **Services** et continuez.
    
    Si le service n’a pas correctement démarré, dans Outils d’administration, ouvrez l’observateur d’événements et passez en revue les erreurs et les avertissements contenus dans la partie **Lync Server** sous **Journaux des applications et des services**.

6.  Une fois que le service **Passerelle de traduction XMPP de Lync Server** est en cours d’exécution, revérifiez les commandes netstat utilisées précédemment. Si vous ne voyez pas les sessions établies ou écoutées, vérifiez et assurez-vous que l' **itinéraire de Fédération XMPP** est correctement configuré dans le générateur de topologies.

7.  Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.

8.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.

9.  Dans le générateur de topologies, sélectionnez le site pour l’itinéraire de Fédération XMPP et vérifiez que l’attribution de l' **itinéraire de Fédération du site** pour la **Fédération XMPP** indique votre serveur Edge ou pool de serveurs Edge comme l’attribution de l’itinéraire de Fédération XMPP sélectionnée.
    
    Si l’attribution de l’itinéraire est incorrecte ou n’est pas définie, cliquez avec le bouton droit sur le site, cliquez sur **Modifier les propriétés**. Activez la case à cocher Fédération XMPP, puis sélectionnez le serveur Edge ou le pool de serveurs Edge correct.

10. Publiez la topologie. Pour plus d’informations, reportez-vous à [publier votre topologie dans Lync Server 2013](lync-server-2013-publish-your-topology.md)
    
    <div class=" ">
    

    > [!TIP]  
    > Bien que cela ne soit pas obligatoire et généralement inutile, vous devrez peut-être redémarrer les serveurs Edge

    
    </div>

11. À l’aide du processus netstat utilisé précédemment, vérifiez que le serveur Edge écoute ou a des sessions établies sur le port 5269 et le port 23456.

12. Si vous ne voyez toujours pas les sessions attendues, passez en revue l’observateur d’événements pour tenter de trouver les causes possibles de ce problème de communication.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Exemple de configuration XMPP dans Lync Server 2013 – Fédération XMPP avec Google Talk](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[Gérer les partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

