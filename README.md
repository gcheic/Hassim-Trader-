{
            // Récupérer les valeurs entrées par l'utilisateur
            const capital = parseFloat(document.getElementById('capital').value);
            const riskPercentage = parseFloat(document.getElementById('risk').value);
            const pips = parseFloat(document.getElementById('pips').value);
            const pipValue = parseFloat(document.getElementById('pipValue').value);

            // Vérification des valeurs
            if (isNaN(capital) || isNaN(riskPercentage) || isNaN(pips) || isNaN(pipValue)) {
                alert("Veuillez entrer des valeurs valides.");
                return;
            }

            // Calcul du risque en dollars
            const riskAmount = (capital * riskPercentage) / 100;

            // Calcul de la taille du lot
            const lotSize = riskAmount / (pips * pipValue);

            // Calcul du gain potentiel en pourcentage
            const profitPercentage = (pips * pipValue * lotSize) / capital * 100;

            // Affichage des résultats
            document.getElementById('lotSize').textContent = lotSize.toFixed(2);
            document.getElementById('profitPercentage').textContent = profitPercentage.toFixed(2);
        }
    </script>
</body>
</html>
