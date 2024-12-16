document.addEventListener('DOMContentLoaded', () => {
    const initializeButtonOptions = (container = document) => {
        container.querySelectorAll('[data-group]').forEach(group => {
            const buttonOptions = group.querySelectorAll('.button-option');
            if (buttonOptions.length > 0) {
                const activeButtonOption = group.querySelector('.button-option.is-active');
                if (!activeButtonOption) {
                    const firstButtonOption = buttonOptions[0];
                    firstButtonOption.classList.add('is-active');
                    const input = firstButtonOption.querySelector('input[type="radio"], input[type="checkbox"]');
                    if (input) {
                        input.checked = true;
                    }
                }
            }
        });
    };

    const initializeButtonAddons = (container = document) => {
        container.querySelectorAll('[data-group]').forEach(group => {
            const buttonAddons = group.querySelectorAll('.button-addon');
            if (buttonAddons.length > 0) {
                const activeButtonAddon = group.querySelector('.button-addon.is-active');
                if (!activeButtonAddon) {
                    const firstButtonAddon = buttonAddons[0];
                    firstButtonAddon.classList.add('is-active');
                    const input = firstButtonAddon.querySelector('input[type="radio"], input[type="checkbox"]');
                    if (input) {
                        input.checked = true;
                    }
                }
            }
        });
    };

    const handleClick = event => {
        const button = event.target.closest('.button-option, .button-addon');
        if (!button) return;
        const group = button.closest('[data-group]');
        if (!group) return;

        const isAddon = button.classList.contains('button-addon');
        const buttonSelector = isAddon ? '.button-addon' : '.button-option';

        const activeButton = group.querySelector(`${buttonSelector}.is-active`);
        if (activeButton && activeButton !== button) {
            activeButton.classList.remove('is-active');
            const input = activeButton.querySelector('input[type="radio"], input[type="checkbox"]');
            if (input) {
                input.checked = false;
            }
        }

        button.classList.add('is-active');
        const input = button.querySelector('input[type="radio"], input[type="checkbox"]');
        if (input) {
            input.checked = true;
        }
    };

    document.addEventListener('click', handleClick);
    initializeButtonOptions();

    document.addEventListener('smootify:product_loaded', (event) => {
        const { id, product } = event.detail;

        requestAnimationFrame(() => {
            initializeButtonAddons();
        });
    });
});
